## Scribble Crew, meh...

```haxe
// i swear if this doesn't work... 😡🤬😠
typedef ListType =
{
	name:String,
	role:String,
}

enum GrabType
{
	ROLE;
	NOTHING;
}

class Developers
{
	static var devs(default, never):Array<ListType> = [
		{
			name: "YourFriendOrbl",
			role: "Owner"
		}
	];

	static function main():Void
	{
		loopTrace(ROLE);
	}

	private static function loopTrace(stat:GrabType = NOTHING):Void
	{
		var traceText:String = '\n';
		final width:Int = 40;
		final line:String = repeat("-", width);

		traceText += '\n ${centerText("Developers", width)}';
		traceText += '\n$line';

		for (dev in devs)
		{
			final ending:String = switch (stat)
			{
				case ROLE: ' (${dev.role})';
				case NOTHING: '';
			}
			traceText += "\n|" + centerText('${dev.name}$ending', width - 2) + "|";
		}

		traceText += '\n$line';
		trace(traceText);
	}

	private static function centerText(text:String, width:Int):String
	{
		final centerOffset:Float = (width - text.length) / 2;
		return repeat(' ', Math.floor(centerOffset)) + text + repeat(' ', Math.ceil(centerOffset));
	}

	private static inline function repeat(char:String, amount:Int):String
		return [for (_ in 0...amount) char].join("");
}

```

Returns:
```haxe
/*
                Developers
----------------------------------------
|        YourFriendOrbl (Owner)        |
----------------------------------------
*/
```
