[![Typing SVG](https://readme-typing-svg.demolab.com?font=Roboto&weight=700&size=45&pause=1000&color=FFFFFF&center=true&vCenter=true&repeat=false&width=435&lines=Scribble+Crew%2C+meh...)](https://git.io/typing-svg)
---

> https://discord.gg/zU7NxYqe9M

## **Example**:
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
	/**
		An Array which contains all developers.
	**/
	static var devs(default, never):Array<ListType> = [
		{
			name: "YourFriendOrbl",
			role: "Owner",
		}
	];

	/**
		Main Function.
	**/
	static function main():Void
	{
		loopTrace(ROLE);
	}

	/**
		Function that traces the developer(s).
	**/
	private static function loopTrace(stat:GrabType = NOTHING):Void
	{
		final width:Int = 40;
		final line:String = repeat("-", width);

		var traceText:String = '\n';

		traceText += '\n ${centerText("Developers", width)}';
		traceText += '\n$line';

		for (i => dev in devs)
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

	/**
		Centers the given text.
	**/
	private static function centerText(text:String, width:Int):String
	{
		final centerOffset:Float = (width - text.length) / 2;
		return repeat(' ', Math.floor(centerOffset)) + text + repeat(' ', Math.ceil(centerOffset));
	}

	/**
		Repeats given character a number of times.
	**/
	private static inline function repeat(char:String, amount:Int):String
		return [for (_ in 0...amount) char].join("");
}
```

## **Returns**:
```haxe
/*
                Developers
----------------------------------------
|        YourFriendOrbl (Owner)        |
----------------------------------------
*/
```
