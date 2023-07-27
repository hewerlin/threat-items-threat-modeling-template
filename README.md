# Threat Items Threat Modeling Template

Welcome to Threat Items - A threat modeling tool and template that guides a new threat modeling process.

The threat model is defined with highly interconnected items in a very simple data format and then beautifully rendered.

You will define threats like this:

```
ID: T_0067
Type: Threat
Name: ...
Category: Information_disclosure
Mitigation: M_0090
Status: WILL_BE_TAMED

ID: M_0090
Type: Mitigation
Name: ...
Category: System_design
Status: OPEN
```

This information is parsed and beautifully presented for readers.


## Why threat model?

Threat modeling is a great set of methodologies if you want to build something secure.

You...
- first model your system,
- then come up with threats,
- then plan how you mitigate those threats,
- then actually implement the mitigations and
- finally end up with a (hopefully) secure system!

Let's go!



## Can I see this in action?

Sure!

[See a deployment of a fresh and unchanged template, ready to receive your valuable thoughts!](https://hendrik.ewerlin.com/threat-items-threat-modeling-template/)

The template was generalized from a threat model about E2EE medical image link shares Hendrik created for his master thesis.
[See how this looks if you have a real system and dozens of threats and mitigations!](https://hendrik.ewerlin.com/masterarbeit/threat-model/)



## How does this work?

This software is made from two parts:


### The `KVItems Browser` at `index.htm`

This is a single-file browser application that can read and display files in the [very simple KVItems data format](https://kvitems.com/Basics).

It ...
* reads KVItems (data items with key/value properties) from [`items.kvi`](items.kvi) (which includes files from [`threat-model/`](threat-model/))
* adds reverse references
* checks schema and maybe adds schema validation errors
* renders a beautiful document with views and detail information.

By itself, it knows nothing about threat modeling.


### The `threat-model` folder

The [`threat-model`](threat-model/) folder has all the items that together form the threat model.

They are more or less meta.

- [`m-system-model.kvi`](threat-model/m-system-model.kvi) is where you define your system model.
- [`t-threats-and-mitigations.kvi`](threat-model/t-threats-and-mitigations.kvi) is where you define your threats and mitigations.

The majority of the threat modeling will be there.

If you want to adjust categories and status values, views or introduction and conclusion texts, or track your TODOs, find the associated items in the [`threat-model/a-.....`](threat-model/) and [`threat-model/y-.....`](threat-model/) files.

If you feel like wanting to add new properties or types - or redefine what a threat model even is - own [`threat-model/z-schema.kvi`](threat-model/z-schema.kvi).



## Why should I use this?

If you need motivation why you should threat-model...
- Consider this: How would you even know if your system is secure, if you have not actively considered threats and mitigations? 🤷‍♂️

Why use this exact tool?
- **Threat modeling works great with interconnected items!**
- The [KVItems data format](https://kvitems.com/Basics) is super simple, pleasent to write, easily read by humans and machines and has no validation errors except for those that we define ourselves.
- The approach is highly flexible! You can easily add new properties and even new types. If you need something more or different, you can just define it and voilà! You are not stuck with a software that only knows some exact enumeration values and has no chance to add something custom. If some constraint annoys you right now, you can just turn it off.
- Reverse references are super helpful. Whenever you link something, you will be able to follow the reverse link at the linked item. Example: If your Threat has `Category: Information_disclosure`, you will find a `Category-of: <Your Threat>` reverse reference at the item with `ID: Information_disclosure`. Your document is highly connected and can be browsed in both directions. This allows for a great exploration experience.
- Thanks to views, we can have both: Overview and detail information. Different views show the same data from different angles and let us focus on different concerns.
- The format is text-based and can easily be branched and merged in version control systems without breaking.
- No need to install complex tools. Everything is contained in a single HTML file that needs to be served. And then, there's your threat model data.



## How can I get started?

- [Download as ZIP](https://github.com/hewerlin/threat-items-threat-modeling-template/archive/refs/heads/main.zip) / Fork this repository / Clone this repository / Use the "Use this template" action on GitHub.
- Serve the files with your favorite static file server. For example: If you have `npm` installed, run `npx serve`.
- Browse [`index.htm`](index.htm).
- Adjust the files in the [`threat-model`](threat-model/) folder.
- Some editors know how to auto-complete references, even when the IDs are defined in different files. I use Visual Studio Code, which works awesome out of the box. But, well... Any editor will do. This is just text!
- The file [`threat-model/a-2-progress.kvi`](threat-model/a-2-progress.kvi) has step-by-step recommendations how to actually perform a threat modeling process for a real system.
- If you are new to threat modeling: Be bold. Have no fear. Get going.
- Own the process. Have fun! 😊



## Ideas? Questions? Feedback?

Feel free to contact `hendrik@ewerlin.com` or create issues.

I will be glad to receive your thoughts on the project, so that it can improve! 😍



## Thanks

Thank you so much, [Feather Icons](https://feathericons.com/), for the beautiful icons! 😘
