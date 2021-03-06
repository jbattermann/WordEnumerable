IEnumerable<string> and corresponding IEnumerator<T> implementation which takes an input string and lets you iterate over its words, e.g. like this:


```
using WordEnumerable

namespace TextEnumerable.Sample
{
    class Program
    {
        private const string _sampleText =
            @"Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.";

        static void Main(string[] args)
        {
            var wordEnumerable = new WordEnumerable.WordEnumerable(_sampleText);
            foreach (var word in wordEnumerable)
                Console.WriteLine(word);

            Console.WriteLine(wordEnumerable.Any(w => w == "Lorem"));
        }
    }
}
```


(c) of the underlying TextParser.cs bits go to Jonathan Wood (see his article at http://www.blackbeltcoder.com/Articles/strings/a-text-parsing-helper-class), I just merely wrapped the enumeration parts around it to make a tiny bit more usable.
