# 정의

네임스페이스 : `System.Linq`

# All


**시퀀스의 모든 요소가 특정 조건에 맞는지 확인한다.**

```csharp
public static bool All<TSource> (this System.Collections.Generic.IEnumerable<TSource>
 source, Func<TSource,bool> predicate);
```

****

> 소스 시퀀스의 모든 요소가 지정된 조건자의 테스트를 통과하거나 시퀀스가 비어 있으면 `true` 를 반환하고 그렇지 않으면 `false`를 반환
> 

### 예제코드

```csharp
class Pet
{
	public string Name { get; set; }
	public int Age { get; set; }
}

public static void AllEx()
{
	// Pet 배열을 만든다.
	Pet[] pets = { new Pet { Name="Barley", Age=10 },
								new Pet { Name="Boots", Age=4 },
								new Pet { Name="Whiskers", Age=6 } };

	// 모든 pet이름을 확인한다
	// 이름이 'B'로 시작하는지 
	bool allStartWithB = pets.All(pet =>
                                  pet.Name.StartsWith("B"));

	Console.WriteLine(
	    "{0} pet names start with 'B'.",
	    allStartWithB ? "All" : "Not all");

}
// 코드 결과 : 
//
//  Not all pet names start with 'B'.
```

- `pets[2].name`인 `Whiskers`가 이름이 “B”로 시작하진 않기 때문에 모든 요소가 조건에 만족하지 않아 `allStartWithB`에 `false` 반환

# Any



**시퀀스에 요소가 하나라도 있는지 확인한다.**

```csharp
public static bool Any<TSource> (this System.Collections.Generic.IEnumerable<TSource> 
source);
```

> 소스 시퀀스에 요소가 하나라도 있으면 `true`를 반환하고 그렇지 않으면 `false`를 반환
> 

### 예제코드

```csharp
string target = "C# is Programming";

if (target.Any(x => Char.IsLower(x)))
    Console.WriteLine($"문자열 안에 소문자가 포함 되어 있습니다.");
else
    Console.WriteLine($"문자열 안에 소문자가 포함되어 있지 않습니다.");

// 코드 결과 : 
//
// 문자열 안에 소문자가 포함 되어 있습니다.
```

- `target`문자열에 소문자가 하나이상 있기때문에 `true`를 반환한다