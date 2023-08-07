---
layout: post
title:  "Unity Utilities"
date:   2022-12-01 00:00:00 -0400
categories: 
thumbnail: "/assets/heros/Unity%20Utilities.png"
tag: uma
---

I've put out a handful of open-source Unity utilities to extend and complete the editor's functionality. These are features I really wish would come stock, so I've done my best to make them seem as native as possible.

@row
## Get

@row
![Get](/assets/unity/Get.png)
@column
<div class="pbox">
Get is an attribute that magically fills your component references.

[Download from GitHub](https://github.com/bgsulz/Get-for-Unity){: .btn}
</div>
@row

Simply write:

```cs
[Get] public Renderer myRenderer;
```

and the serialized field will automatically fill with the Renderer attached to this GameObject. (It's like you called `GetComponent`.)

`GetInChildren`, `GetInParent`, `Find` (searches the hierarchy) and `FindAssets` (searches the asset database) are also supported. If there are multiple options, a searchable dropdown window allows for rapid browsing and selection.

For ScriptableObject fields, a `+` button also appears for creating new SOs on the fly.

More details and functionality are described on the Get GitHub repository.

@row
## Reflectors

@row
![Reflectors](/assets/unity/Reflectors.png)
@column
<div class="pbox">
Reflectors are a collection of utilities that use a custom API for very fast reflection.

[Download from GitHub](https://github.com/bgsulz/Reflectors-for-Unity){: .btn}
</div>
@row

The most useful is `PropertyReference`.

Suppose you're writing a UI component to display a numerical stat. If you want to reuse this component to display numbers stored in different objects -- a `float strength` in one script, a `float mana` in another -- you have a few options. But what they all have in common is that they're editor-averse OOP nonsense that overcomplicate your project's architecture.

Wouldn't it be great to just write:

```cs
public PropertyReference<float> floatProp;
```

You can! Just drop in your object and choose the propertt in the editor. Nested properties are supported! The "catch" is that you need to initialize the object before using it:

```cs
void Start()
{
    floatProp.Initialize();
}
```

Like all utilities in this package, this uses reflection to compile a Linq expression tree that accesses the property. After Initializing, access is nearly compile-time fast.

```cs
void Update()
{
    // Yes, you can write this with no fear!
    textMesh.text = floatProp.Value.ToString();
}
```

More examples are provided on the Reflectors GitHub repository.

@row
## Either

@row
![Either](/assets/unity/Either.png)
@column
<div class="pbox">
Either is a serializable union-esque type for Unity. It works like popular package OneOf but with Unity-specific goodies like Inspector support.

[Download from GitHub](https://github.com/bgsulz/Either-for-Unity){: .btn}
</div>
@row

This type is useful for unifying types with similar functionality that can't share an interface. For example, say you have an audio management system based on a robust `Sound` class with support for variable pitch, volume fades, round robins, etc. But making a new `Sound` for every `AudioClip` is a hassle. To test out a new sound and/or allow for simpler cases, you can write:

```cs
public Either<Sound, AudioClip> clip;

//Play the sound like so:
clip.Do(
    sound => sound.Play(SoundManager.Instance),
    audioClip => AudioManager.PlayOneShot(audioClip);
);
```

More example uses are provided on the Either GitHub repository. Try it -- you'll keep finding uses for it!