# 정의

네임스페이스 : `System.Linq`

# All


**시퀀스(컬렉션) 의 모든 요소가 특정 조건에 맞는지 확인한다.**

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


**시퀀스에 요소가 하나라도 있는지 확인하거나 특정 조건에 맞는 요소가 있는지 확인합니다.**

```csharp
public static bool Any<TSource> (this System.Collections.Generic.IEnumerable<TSource> 
source);
```

> 소스 시퀀스에 요소가 하나라도 있거나 특정 조건에 맞는 요소가 있으면 `true`를 반환하고 그렇지 않으면 `false`를 반환
> 

### 예제코드

```csharp
class Pet
{
    public string Name { get; set; }
    public int Age { get; set; }
    public bool Vaccinated { get; set; }
}

public static void AnyEx3()
{
    // Pet 배열을 만든다.
    Pet[] pets =
        { new Pet { Name="Barley", Age=8, Vaccinated=true },
          new Pet { Name="Boots", Age=4, Vaccinated=false },
          new Pet { Name="Whiskers", Age=1, Vaccinated=false } };

		// 1살 초과인 애완동물이 예방접종을 맞지 않았는지 확인
    bool unvaccinated =
        pets.Any(p => p.Age > 1 && p.Vaccinated == false);

    Console.WriteLine(
        "There {0} unvaccinated animals over age one.",
        unvaccinated ? "are" : "are not any");
}

// 코드결과 : 
//
//  There are unvaccinated animals over age one.
```

- `pets[1]` 가 `age`가 1보다 크고 `Vaccinated == false`에 만족하기 때문에 `unvaccinated`에 `true` 반환

## 정리

### All

- **시퀀스에 모든요소가 특정 조건에 만족하면 `true` 아니면 `false`**

### Any

- **시퀀스에 요소가 하나라도 있으면 `true` 아니면 `false`**
- **특정 조건에 맞는 요소가 하나라도 있으면 `true` 아니면 `false`**