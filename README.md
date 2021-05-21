# FSharp-Resources
This repository contains a curated list of blogs, articles, videos and tutorials related to F#.

## General information

- ``Idisposable`` interface
    - The ``IDisposable`` Interface is defined in the ``System namespace``. The ``Idisposable`` interface releases un-managed resources, objects that are no longer needed as soon as it occurs and automatically frees up the memory. 
    - Only time we use ``new`` in F# is when we use the ``Idisposable`` interface

- [``use`` keyword and ``using`` function (Resource Management)](https://docs.microsoft.com/en-us/dotnet/fsharp/language-reference/resource-management-the-use-keyword
)

### Data Types
- ``unit``:
    - Uses of ``unit``:
        1. When there is a side effect
        2. When the code is not deterministic
        3. When you want to evaluate it another time

- ``String``
    - [Interpolated String](https://docs.microsoft.com/en-us/dotnet/fsharp/language-reference/interpolated-strings)

### File structures and Hierarchies
- File-order:  A "later file" can access the modules defined in "earlier file"

- Namespaces

- Modules
 

## Blogs
- [Tomas Petricek](http://tomasp.net/)

## Tutorials
- [FSharpForFunAndProfit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)

#### Data Structures
- ``Set``
    - [VisualFSharp Set](http://www.visualfsharp.com/collections/sets.htm)

## YouTube Channels

- [Ben Gobeil](https://www.youtube.com/channel/UCX7iFEPRPubYZyU-e-END5A)
- [7sharp9](https://www.youtube.com/user/Dethomas75)
- [The Dev Owl](https://www.youtube.com/channel/UCOX5DkLyqctM-wkOAU_mUpA)

## Topic wise all resources

- **Async Programming**
    - [The Dev Owl](https://youtu.be/u2SlQ5WdL2k)
    - [Ben Gobeil](https://youtu.be/eMSZSUbeexc)
    - [Task Parallel Library C#](https://www.pluralsight.com/guides/async-programming-task-parallel-library)
    - [Async Await C#](https://www.pluralsight.com/guides/csharp-async-await-keywords-getting-started)

- **Computation Expression (CE)**
    - [Ben Gobeil](https://www.youtube.com/watch?v=pC4ZIeOmgB0)
    - Notes:
        1. Return from CE block a type of CE expression         
            - define ``return``
        2. ``let!``
            - Define ``bind``
        3. ``<*>``
            - Define ``apply``
        4. ``and!``
            - Define ``mergeSources``
                - Define ``zip``
            - Define ``bindReturn``
                - Define ``map``
        5. ``return!``
            - Define ``returnFrom``
        6. Return nothing or unit inside CE block
            - Define ``zero``
        7. Single expression inside CE block
            - Define ``yield``
        8. Combine multiple expressions inside CE block (implicit yield)
            - Define ``combine`` and ``delay``
        9. Defer execution or lazily evaluated expression 
            - Define ``run``
                -  don't execute in delay, but execute it in combine and run
        10. Builder pattern
            - Design pattern to build complex objects (with lots of fields and subfields)


## Terminologies
- Point Free Code
    - Point-free style means that the code doesn't explicitly mention it's arguments, even though they exist and are being used.
    - [What is “point free” style (in Functional Programming)?](https://stackoverflow.com/q/944446/5672613)

- Eager vs Lazy evaluation
    - F# is eagerly evaluated

- Functor, Applicative & Monad
    - Functor 
        - Something that's implements ``map``

    - Applicative 
        - Something that can define ``apply`` and ``return``
        - Applicative workflows are parallel 
    
    - Monad 
        - Something that can define ``bind`` and ``return`` 
        - Monadic workflows are sequential

    - ``Map`` and ``Bind`` are used when you have some Container type like ``Option`` or ``Async``. Container, because it wraps some generic type ``'T`` in it (so you get ``Option<'T>`` or ``Async<'T>``). Now you want to actually change the value or even the type that is wrapped by the container but you want to keep the type of the container (it should stay an Option or an Async after the transformation).  An ``Option<string>`` could be transformed into an ``Option<int>``. This is where ``map`` and ``bind`` come into play. ``map`` unwraps the value from the container, executes some function on the value (e.g. ``String.length`` on a ``string``, which returns an ``int``) and wraps the return-value in the container type (by the way, a type that has such a ``map`` function is called a ***functor***). But what if the function you are executing is itself returning a container value (e.g. ``Option<int>``)? This is where ``bind`` comes into play. Bind does not wrap the return-value of the function in the container, it just returns the value (this is one necessary function of a ***monad*** btw).

- Side-effects

- Currying

- Partial Application


## Articles
- Miscellaneous
    - [What I wish I knew when learning FSharp](https://danielbachler.de/2020/12/23/what-i-wish-i-knew-when-learning-fsharp.html) by Daniel Bachler

- Topic wise
    - Active Pattern
        - [Pattern Matching in F# Part 2 : Active Patterns](https://www.developerfusion.com/article/133772/pattern-matching-in-f-part-2-active-patterns/)
    - DataReader
        - [Using a DataReader like a List in F#](https://www.codeproject.com/Articles/95656/Using-a-DataRader-like-a-List-in-F)
    - ``Inline`` keyword
        - [The Burning Monk](https://theburningmonk.com/2011/12/f-inline-functions-and-member-constraints/)
        - [Statically Resolved Type Parameters(SRTP)](https://docs.microsoft.com/en-gb/dotnet/fsharp/language-reference/generics/statically-resolved-type-parameters)
    - ``open`` keyword
        - [MSDN](https://docs.microsoft.com/en-us/dotnet/fsharp/language-reference/import-declarations-the-open-keyword)

## Database
- **Transaction**
    - [FsProject Transaction](https://fsprojects.github.io/FSharp.Data.SqlClient/transactions.html)
    - [Beware of TransactionScope](https://www.thinktecture.com/en/entity-framework-core/transactionscope-lifetime-extension-with-csharp-8-0/)

## Web Development
- [Giraffe](https://github.com/giraffe-fsharp/Giraffe)

## Libraries
- [FSharp.Data](https://fsprojects.github.io/FSharp.Data/)
    - The FSharp.Data package implements core functionality to access common data formats in your F# applications and scripts. It contains F# type providers for working with structured file formats (CSV, HTML, JSON and XML) and helpers for parsing CSV, HTML and JSON files and for sending HTTP requests.

- App Configuration
    - [FsProjects AppSettingsProvider](https://fsprojects.github.io/FSharp.Configuration/AppSettingsProvider.html)