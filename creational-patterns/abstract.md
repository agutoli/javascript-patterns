# Definition
Provide an interface for creating families of related or dependent objects without specifying their concrete classes.

# Why should I use

You may be wondering why you would want to leave the responsibility of the construction of objects to others rather than simply calling a constructor function with the new keyword directly. The reason is that that constructor functions are limited in their control over the overall creation process and sometimes you will need to hand over control to a factory that has broader knowledge.

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
