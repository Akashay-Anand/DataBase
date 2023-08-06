# Data Model
> Collection of conceptual tools for describing data, data relationships, data semantics, and consistency constraints.


## ER Model
> It is a high-level data model based on a perception of a real world that consists of a collection of basic objects, called entities and of relationships among these objects.  
<br/>

### Entity:
> An Entity is a “thing” or “object” in the real world that is distinguishable from all other objects.
> Entity can be uniquely identified. (By a primary attribute, aka Primary Key)  
> Strong Entity: Can be uniquely identified.  
> Weak Entity: Can’t be uniquely identified., depends on some other strong entity.
<br/>

> Entity set: It is a set of entities of the same type that share the same properties, or attributes.

### Attributes
> An entity is represented by a set of attributes.   
> For each attribute, there is a set of permitted values, called the domain, or value set, of that attribute.

#### Types of Attributes

> 1. Simple   
>> 1. Attributes which can’t be divided further.  
>> 2. E.g., Customer’s account number in a bank, Student’s Roll number etc.  
> 2. Composite  
>> 1. Can be divided into subparts (that is, other attributes).  
>> 2. E.g., Name of a person, can be divided into first-name, middle-name, last-name.  
>> 3. If user wants to refer to an entire attribute or to only a component of the attribute.  
>> 4. Address can also be divided, street, city, state, PIN code.  
> 3. Single-valued  
>> 1. Only one value attribute.  
>> 2. e.g., Student ID, loan-number for a loan.  
> 4. Multi-valued  
>> 1. Attribute having more than one value.  
>> 2. e.g., phone-number, nominee-name on some insurance, dependent-name etc.  
>> 3. Limit constraint may be applied, upper or lower limits.  
> 5. Derived  
>> 1. Value of this type of attribute can be derived from the value of other related attributes.  
>> 2. e.g., Age, loan-age, membership-period etc.  
> 6. NULL Value  
>> 1. An attribute takes a null value when an entity does not have a value for it.  
>> 2. It may indicate “not applicable”, value doesn’t exist. e.g., person having no middle-name  
>> 3. It may indicate “unknown”.  
>>> 1. Unknown can indicate missing entry, e.g., name value of a customer is NULL, means it is missing as name must have some value.  
>>> 2. Not known, salary attribute value of an employee is null, means it is not known yet.  

<br/>

### Relationships Constraints
> 1. Mapping Cardinality / Cardinality Ratio
>> 1. Number of entities to which another entity can be associated via a relationship.
>> 2. One to one, Entity in A associates with at most one entity in B, where A & B are entity sets. And an entity of B is associated with at most one entity of A.
>>> 1. E.g., Citizen has Aadhar Card.
>> 3. One to many, Entity in A associated with N entity in B. While entity in B is associated with at most one entity in A.
>>> 1. e.g., Citizen has Vehicle.
>> 4. Many to one, Entity in A associated with at most one entity in B. While entity in B can be associated with N entity in A.
>>> 1. e.g., Course taken by Professor.
>> 5. Many to many, Entity in A associated with N entity in B. While entity in B also associated with N entity in
>>> A.
>>> 1. Customer buys product.
>>> 2. Student attend course.
> 2. Participation Constraints
>> 1. Aka, Minimum cardinality constraint.
>> 2. Types, Partial & Total Participation.
>> 3. Partial Participation, not all entities are involved in the relationship instance.
>> 4. Total Participation, each entity must be involved in at least one relationship instance.
>> 5. e.g., Customer borrow loan, loan has total participation as it can’t exist without customer entity. And customer has partial participation.
>> 6. Weak entity has total participation constraint, but strong may not have total.



<br/>
<br/>

<img width="557" alt="image" src="https://github.com/Akashay-Anand/DataBase/assets/82114930/7781f246-c480-4e7f-b5e0-b561e0e586c4">




