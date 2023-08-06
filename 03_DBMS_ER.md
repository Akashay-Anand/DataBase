# Extended ER Features

## Specialisation
> Specialisation is splitting up the entity set into further sub entity sets on the basis of their functionalities, specialities and features.  
> It is a Top-Down approach  
> e.g., Person entity set can be divided into customer, student, employee. Person is superclass and other specialised entity sets are subclasses.  
>>  We have __“is-a”__ relationship between superclass and subclass.  
>> Depicted by triangle component.  

## Generalisation
> It is just a reverse of Specialisation.  
> DB Designer, may encounter certain properties of two entities are overlapping. Designer may consider to make a new generalised entity set. That generalised entity set will be a super class.  
> “is-a” relationship is present between subclass and super class.   
> e.g., Car, Jeep and Bus all have some common attributes, to avoid data repetition for the common attributes. DB designer may consider to Generalise to a new entity set “Vehicle”.  
> It is a Bottom-up approach.  

## Attribute Inheritance
> Both Specialisation and Generalisation, has attribute inheritance.  
> The attributes of higher level entity sets are inherited by lower level entity sets.  
> E.g., Customer & Employee inherit the attributes of Person.  

## Participation Inheritance
> If a parent entity set participates in a relationship then its child entity sets will also participate in that relationship.

## Aggregation
> How to show relationships among relationships? - Aggregation is the technique.
>  Abstraction is applied to treat relationships as higher-level entities. We can call it an Abstract entity.
> Avoid redundancy by aggregating relationships as an entity set itself.

