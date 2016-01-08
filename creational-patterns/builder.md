# Definition
Separate the construction of a complex object from its representation so that the same construction process can create different representations.

# Why should I use

The most common motivation for using Builder is to simplify client code that creates complex objects. The client can still direct the steps taken by the Builder without knowing how the actual work is accomplished. Builders frequently encapsulate construction of Composite objects (another GoF design pattern) because the procedures involved are often repetitive and complex.

# Example

    function People(firstName, lastName) {
      this.firstName = firstName;
      this.lastName = lastName;

      this.fullname = function() {
        console.log("Fullname: ", this.firstName, this.lastName);
      }
    }


    function PeopleFactory() {
      this.create = function(firstName, lastName) {
        return new People(firstName, lastName);
      }
    }


    var peopleFactory = new PeopleFactory();
    var people = peopleFactory.create("Andrew", "S. Tanenbaum");
    console.log(people.firstName);
    console.log(people.fullname());
