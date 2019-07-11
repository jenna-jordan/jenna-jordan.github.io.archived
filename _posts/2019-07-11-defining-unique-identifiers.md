---
title: Defining Unique Identifiers - a conceptual analysis
published: true
permalink: /blog/defining-unique-identifiers
toc: true
toc_sticky: true
header:
    image: assets/images/header_identifiers.jpg
    caption: # optional
tags:
  - Random Thoughts
  - Philosophy
  - IS590TH
---

**Note**: This was originally written as a final paper for IS590TH: Theories of Information, in May 2019. I've edited it slightly for this blog post.

## Introduction

Generally speaking, a Unique Identifier (UID) is an inscription that represents (no more than) one entity within a given system. UIDs are essential to the functioning of modern information systems, so it is important to understand and define what a UID is and how it should be used.

In ["Identifiers for the 21st Century"](https://doi.org/10.1371/journal.pbio.2001414), McMurry et al. provides guidelines for creating good unique identifiers. However, while they outline the desirable characteristics of a UID, they refrain from stating which characteristics are necessary for an identifier to truly qualify as a UID, and which are merely good practice. In ["Sense and Reference on the Web"](http://dx.doi.org/10.1007/s11023-011-9230-6), Halpin examines a specific type of identifier, the URI (uniform resource identifier), but also refrains from defining unique identifiers more generally outside of the context of the web.

In this post, I will define unique identifiers by deducing their essential properties.

## What is the purpose of a UID?

Information systems exist to represent or describe some aspect of the real world. Entities are the specific things that we are describing through their attributes and relationships. For example, think of a person. You may wish to record specific attributes of this person, such as their name, age, eye color, hair color, height, etc. You may wish to describe their role within the system by establishing relationships with other entities - what company they are employed by, who their parents are, or what objects they own. But how can you identify this person? In natural language, you would probably use their name. But what if there are multiple people with the same name? You might add other attributes - "the Jane with the brown hair", or "the Jane who works for B Corp." You may need to use multiple attributes to identify the intended person. However, the combination of these attributes (which can uniquely identify Jane) is not a UID.

Think about what is happening in your mind. You have a mental concept of the person, but you cannot telepathically transmit this mental concept to another person. So instead, you describe the person using attributes - things that you associate with your concept of the person. This person's name is Jane. This person is a woman. This person has brown hair, and so on. You know that the other person you are conversing with also has a mental concept of Jane. If you settle on the right combination of attributes (which uniquely identify Jane for both of parties), then you will know that saying "Jane" refers to that specific person.

Just as you cannot telepathically transmit your mental concept of Jane to another person, you cannot transmit this concept to a computer. However, you still want to create a record of Jane in the information system, including all of her attributes. Unlike a person, however, a computer is unable to form a mental concept. Instead, the concept of the person named Jane is represented in the information system by a UID. Let's say Jane's UID is `CH4TW1N`. You can tell the computer that `CH4TW1N`'s name is Jane, that `CH4TW1N` is a woman, that `CH4TW1N` has brown hair, and so on. Thus, a UID functions for a computer like a mental concept functions for a person. In [Fregean](https://en.wikipedia.org/wiki/Gottlob_Frege) terms, a UID is a [proper Name](https://en.wikipedia.org/wiki/Proper_name_(philosophy)), with the entity it picks out as its referent. This is the UID's fundamental purpose in information systems.

## What qualifies as a UID?

Let's first begin by describing an identifier.

An identifier is the **physical, inscribable representation of a concept**. The most common form of a UID is an alphanumeric string stored on a computer. For example, take the alphanumeric string 'CH4TW1N'. On a computer, this alphanumeric string has a specific encoding, and could be translated to some combination of 1s and 0s, which themselves are physically encoded in the computer's hardware. A person could also physically write down 'CH4TW1N' with pen and paper, and it would still be an identifier. However, I could not simply say out loud the phonetic pronunciation of this string and expect it to be an identifier - it cannot be referenced at a later time (unless it was recorded, in which case it is still being physically encoded on some medium). So, the first fundamental trait of an identifier is that it must be an inscription in some form that can be referenced at a later time.

Furthermore this inscription must pick out an entity. An entity could be a concept, a person, a physical object, a place, etc. Anything that has an independent concept in your mind is an entity; more commonly, in English a good rule of thumb is that entities are nouns (person, place, thing, or idea). When two entities are connected in some way, that connection is referred to as a relationship. Relationships are not entities; however, certain relationships may be instances of a concept, which may be an entity. For example, Jane's brother is Martin. The Jane-Martin relationship is not an independent entity, because it cannot mentally exist without either Jane or Martin. However, the concept of being siblings can exist independently, and could be an entity. While translating relationships into entities can be quite complex, attributes are simpler. If Jane has brown hair, then 'brown hair' is an attribute of Jane. However, 'brown hair' is not exclusive to Jane - we can picture brown hair independently of Jane. Attributes can often be entities themselves.

So, we understand what an identifier is. However, unique identifiers have two core additional properties: UIDs must be both **unique** and **unambiguous**.

If a UID is **unambiguous**, any given UID points to exactly one entity ([McMurry et al](https://doi.org/10.1371/journal.pbio.2001414)). For example, if there are two Janes at B Corp, then the identifier 'Jane' will pick out two separate entities. The identifier 'Jane' is ambiguous, and therefore not a UID. If a UID is **unique**, any given entity is assigned exactly one identifier ([McMurry et al](https://doi.org/10.1371/journal.pbio.2001414)). If Jane is assigned the identifier `CH4TW1N` at B Corp, then finds a new job a F Corp where she has the identifier `W4TCH3R`. She later moves back to B Corp, and is assigned the new identifier `3L1Z4PM`. Jane now has two identifiers at B Corp. Thus, Jane does not have a unique identifier, by virtue of the fact that two identifiers will pick her out.

The two core properties of uniqueness and unambiguousness imply two further properties - **identifier stability** and **entity stability**. An identifier is stable if it does not change over time ([McMurry et al](https://doi.org/10.1371/journal.pbio.2001414)). Jane's identifier at B Corp changed over time from `CH4TW1N` to `3L1Z4PM`, so it was not stable. An entity is stable if the entity picked out by an identifier does not change over time ([McMurry et al](https://doi.org/10.1371/journal.pbio.2001414)). If, after Jane left B Corp, her `CH4TW1N` identifier was reassigned to Julia, then it is not stable. In other words, *an identifier's uniqueness and unambiguousness must persist over time*.

These properties of uniqueness, unambiguity, identifier stability, and entity stability can only be enforced if the UIDs exist within a system. Theoretically, this system would contain every possible UID, whether it is currently mapped to an entity or not. In this system, a UID could exist in one of three possible states: not yet assigned to an entity, currently assigned to a single entity, or retired (was assigned to an entity, which for some reason was removed from the system). A UID can only travel one way along this path - it cannot go backwards from being removed from the system to being assigned to entity. In this system, a UID isn't really created or deleted, merely assigned. And *a UID cannot be reassigned*, because that would result in the entire system failing to meet the required properties of unambiguity and identifier stability.

## How is a UID created?

The fact that a UID must exist within a system of all possible UIDs implies that there are a finite number of possible UIDs within the system - and furthermore, that UIDs must obey certain rules.

When a system is created in order to record information about entities (which will have UIDs), the set of all possible UIDs must be defined. In practical terms, this means that a UID can be defined by a regular expression; in linguistic terms, this means that a UID must be describable by a formal grammar.

For example, let's say that B Corp's system defines a UID as a string of alphanumeric character of length 7. There are 26 letters and 10 digits, and 36^7 is 78,364,164,096. This system of UIDs can identify over 78 billion entities - more than sufficient. Most of these UIDs will never be assigned, and thus never need to enter the database. They will never leave the first stage. Some UIDs will be used to identify employees, and thus enter the second stage. The UID will be entered into a database and be assigned attributes with specific values. Some of these UIDs may be retired - for example, if an employee passes away. However, these retired UIDs must never be used again - which means that the physical system must still keep track of them, if only to prevent their reassignment.

How these UIDs are actually generated is not an issue, so long as they follow these simple rules: *they must be formed from a formal grammar's production rules, and once assigned to an entity they must never be reassigned*.

## The question of meaning

It is generally regarded as bad practice to embed meaning within UIDs. When meaning is embedded in a UID, it may become easy to confuse a UID with an attribute. However, while a UID's value could be considered an attribute of the entity, the UID's purpose is to stand in for the entity itself - and thus is not an attribute. There is one fundamental distinction between UIDs and attributes: while an attribute's value may change, a UID may not. Thus, if a UID's value is based on an attribute's value, and that attribute's value changes, confusion may ensue. The UID cannot be changed, or the entire UID system will be invalidated. But a person looking at the UID may make the wrong assumption. Suppose, for example, that the first character 'C' in Jane's UID means that she is a level C employee. But Jane recently got promoted to level B. Her UID cannot be changed and still be valid, but her UID also incorrectly implies that she is a level C employee.

Encoding meaning in a UID is dangerous - but is it invalid? Even though someone might make the wrong assumption by only looking at Jane's UID, so long as the UID remains unique, unambiguous, and stable over time, it is still a valid UID. Rather than a person making an erroneous assumption, the reverse should be true - individuals must disassociate meaning from the UID since it cannot be guaranteed to be correct. As [McMurry et al](https://doi.org/10.1371/journal.pbio.2001414) recommend, "Meaning should only be embedded if it is indisputable, unchangeable and also useful to the data consumer."

## UIDs can only be unique within a local context

When a UID system is created, it is usually created to work within a specific context - a company, a university, a government database, etc. Outside of the system, a UID's uniqueness cannot be guaranteed. However, data systems frequently need to be integrated. And so this system, this context, needs to be defined. This is frequently accomplished by assigning the context itself to a unique identifier (commonly denoted as a prefix followed by a colon). The prefix designates which system a UID belongs to, and thus becomes a part of the identifier itself. Together, all of the contexts and their prefixes form a new system - a new context that is the union of all sub-contexts contained within. And so, the prefix becomes a part of this new system's UID formal grammar.

If the prefix is to become part of the UID, then it too must follow the rules outlined thus far: to be unambiguous (one prefix designates exactly one context), to be unique (a context has exactly one prefix), and to be stable (prefixes do not change over time or refer to different contexts over time). This stability over time is what necessitates the use of prefixes - for even if the local UIDs happen to still be unique and unambiguous in the merged system, there is no guarantee that this will still be the case for future states of the system, as each local UID's uniqueness is only guaranteed within its local system. Whenever one system is merged with another, namespaces and prefixes must be designated, or the identifier cannot qualify as a unique identifier.

Unique context identifiers can ensure the new UID system is unambiguous (each UID picks out exactly one entity); however, ensuring that the new UID system is unique is more complicated. For example, suppose B Corp and F Corp are both acquired by L Corp, which combines all employee UIDs into one system using context identifiers. Suppose B Corp's prefix is `B` and F Corp's prefix is `F`. Suddenly, we have a problem. `B:CH4TW1N` and `F:W4TCH3R` both refer to Jane, and so the entire UID system no longer fulfills the uniqueness requirement.

To solve this problem, L Corp should find the combination of stored attributes which can uniquely identify a person. For example, B Corp and F Corp will likely store attributes such as her first name, last name, and birthdate. Together, these attributes may uniquely identify an employee (though there is no guarantee). Or they may have stored other attributes for security purposes, such as fingerprints or a retinal scan. These are much more likely to guarantee uniqueness. Regardless, having a a combination of attributes that can uniquely identify an entity can help a system enforce its UID uniqueness. In database terms, this is known as a compound primary key. It's also possible that a single attribute may uniquely identify Jane, such as her social security number - a UID from a much broader system. L Corp can now create a mapping from one context to another. However, this is only the first step in the solution.

The real problem is that the two local contexts identify entities of the same type (person), thus creating the danger of overlap (non-uniqueness). It can be generalized that in a UID system that contains multiple contexts, besides the prefix itself being unique, the entity type that the prefix describes must also be unique. This means that in order for L Corp to have a UID system, they must create a formal grammar and then assign a new UID to each employee. L Corp may wish preserve the old B Corp and F Corp UIDs for historical purposes, and so may create mappings between the UID systems, but only by establishing a completely new set of UIDs can L Corp ensure that each employee has an unambiguous and unique identifier.

Suppose that a UID system identified multiple types of entities - people, locations, objects, etc. If any one of these entity types overlaps with another UID system, the same process of (1) finding the combination of attributes that can uniquely identify an entity, (2) mapping between the systems, and then using that mapping when (3) creating a completely new UID system must be followed. (This also implies that it is good practice for a local UID system to identify one entity type, but this is not a necessary condition for UIDs.)

It is important to note that there is no such thing as a truly global UID - nor is it desirable for there to be a global UID system (though that discussion is outside the scope of this post). For there to be a truly global UID, all entities - all information - would have to exist within a single information system. Even with the existence of the internet, this is not feasible. Therefore, the issue of context identifiers, namespaces, prefixes, and mappings between systems is unavoidable - any definition of a UID must discuss both local identifiers and context identifiers as components of an overall UID.

## Once again, the question of meaning

For local (single context) UIDs, embedding meaning is strongly discouraged (though not disqualifying). However, when context identifiers and prefixes are added to the mix, embedded meaning quickly becomes impossible to escape. Many prefixes are acronyms or short words, describing either the organization that produced the UID or the type of entity that the UID set describes (or a combination of the two). Should meaning be a disqualifying characteristic of UIDs, no non-local UID with a context identifier could be considered a UID - and as I have already established, any definition of UIDs must consider context identifiers as an essential aspect of a UID. Therefore, while opacity is a recommended characteristic for UIDs, it is not a necessary property. So long as the UID still follows the production rules of its formal grammar, any meaning, purposefully embedded or not, is irrelevant.

## Contexts may change over time, and other attributes

Despite the best of intentions, it is inevitable that a UID system will change over time. A UID may need to be reassigned, or the formal grammar may need to change. When this happens, a completely new UID system is created. UIDs cannot be reassigned, and the set of all possible UIDs have already been defined. By definition, should either of these things happen, it necessitates a distinct system and context, and thus a distinct prefix as well.

This most frequently happens as a result of versioning. A common convention is to append the version number at the end of the original prefix (again embedding meaning in the context identifier). It is important to document this association, so as to avoid both contexts being used in a larger system (as this would introduce a uniqueness problem), as well as to provide a mapping from the old system to the new.

This implies that in addition to context identifiers having a specify entity type (or set) that their local UIDs reference as an attribute, context identifiers also have a specific time period as an attribute. If B Corp changed their production rules (for example, they wish to make their UIDs 5 characters long instead of 7) on January 1, 2018, then the context identifier `bcorp` has the attribute of identifying entities of the type person and the attribute of identifying entities prior to 2018. The context identifier `bcorp_v2` has the attribute of identifying entities during and after 2018. Another property of context identifiers is the formal grammar used to generate all local UIDs. If this set of UIDs are stored on the web, another attribute of the context identifier may be its web address (URL).

However, it is important to distinguish between a context's attributes and a context's identifier. An online location is an attribute, because it is not guaranteed to be stable over time. Within the semantic web community, a web address (URL) is often treated as a unique identifier. This is erroneous, as web addresses have the potential to change from one moment to the next. For a web address to be a UID, the entire system would have to be created anew every second. Perhaps this is feasible - for the web's system to incorporate a timestamp into each context identifier, but it is certainly not practical or desirable. Furthermore, the semantic web community does not argue that this is the case - and so, we are left with the conclusion that web addresses (URLs) are not UIDs, both because they are not stable over time, nor can uniqueness be guaranteed (there is nothing restricting me from copying one webpage exactly at a different web address). I will repeat my point: location is an attribute, not a unique identifier.

## The issue of identity

There is a larger issue at play here, which I will touch on only briefly - the issue of identity. This is absolutely core to the concept of unique identifiers, as each UID must pick out an entity with a distinct identity. However, it is generally accepted that entities may change - Jane can dye her hair blonde, change employers, move to a new location... even change her name. But you would not consider blonde Eliza of P Corp to be a different person. You could argue that she still has the same fingerprints, the same DNA, but even these can change over time. Eliza and Jane are still the same person. When it comes to physical entities like people, identity is fairly easy to grasp, if hard to define. However, identity is not nearly so easily traced when it comes to imaginary entities - countries, corporations, books, etc. When I say imaginary entities, I mean those things that would not exist without people to think them up. A tiger is a tiger, whether human beings ever evolved from great apes or not. But a corporation only really exists in society's collective consciousness. It may be described on paper, have physical offices, and pay employees, but the moment everybody stops believing that the corporation exists, it will cease to exist as an entity (Yuval Noah Harari explores this concept in ["Sapiens"](https://www.ynharari.com/book/sapiens/)). For these types of entities, identity is much harder to trace. What if the corporation changes its name? What if it fires all of its employees, sells all of its offices, and finds new ones? What if it sells a different product? Is it still the same corporation? What is the line that an entity must cross in order to assume a new identity, and thus a new UID? These are questions that must still be considered in order to have a full understanding of unique identifiers - for the meaning of the entity that a UID identifies is essential to the meaning of the UID itself.

## Key Takeaways

Definition of a UID:
1. an inscription produced by a formal grammar
2. refers to exactly 1 entity (unambiguous) at any given time
3. its referred entity has exactly one UID (unique) at any given time
4. the inscription persists over time (identifier stability)
5. the entity to which it refers persists over time (entity stability)

**Remember**

- A UID may be decomposed into a context identifier and a local identifier. In this case, all context identifiers must also follow this definition, wherein the entity referred to is the set of local identifiers.

- When a local identifier violates any of the rules in the definition, a new context is created and a new context identifier must be defined.

- Opacity (lack of inherent or inferred meaning), while highly recommended for UIDs, is not necessary.

## Citations

McMurry JA, Juty N, Blomberg N, Burdett T, Conlin T, Conte N, et al. (2017) Identifiers for the 21st century: How to design, provision, and reuse persistent identifiers to maximize utility and impact of life science data. PLoS Biol 15(6): e2001414. https://doi.org/10.1371/journal.pbio.2001414

Harry Halpin. (2011) Sense and Reference on the Web. Minds Mach. 21, 2 (May 2011), 153-178. http://dx.doi.org/10.1007/s11023-011-9230-6
