# lab1

    
---
###Excersise 02 Let's use curly brackets to create JSON like JavaScript object and add properties and functions to the object.

        var object = {
            name : "Asiri H",
            batch : "SE WD",
            getName : function(){ console.log(this.name);},
            setName : function(name){this.name = name;},
            getBatch : function(){ console.log(this.batch);},
            setBatch : function(){ this.batch = batch; }
        };
        object.setName("Perera and Sons");
        object.getName();
######Excersise 03 To understand the ‘this’ keyword in JavaScript let's do the following,

Declare a global variable named vehicleName in the window object Declare a method named printVehicleName to print out the vehicle name Declare an object named Vehicle(using object literal notation) which have a variable called vehicleName and declare a function named getVehicleName and assign it with the printVehicleName Execute the printVehicleName function and the getVehicleName functions to see the results Correct the getVehicleName to print out the global variable vehicleName using the this keyword

        var vehicleName = "Toyota";
        printVehicleName = function () {
            console.log(this.vehicleName)
        }

        vehicle = {
            vehicleName : "Dumb vehicle",
            getVehicleName: function () {
                // prints Global variable vehicleName = "Toyota"
                // console.log(vehicleName)
                // prints the vehicle name of the object (context) = "Dumb vehicle"
                console.log(this.vehicleName) // this keyword !
            }
        }

        printVehicleName();
        vehicle.getVehicleName();
###Excersise 04 Let's create a separate function using JavaScript closure which accepts the tax percentage and returns a function which accepts the amount and returns the amount after adding tax percentage. Try adding tax percentage to ‘this’ object and check if it works.

        var amount = 100;
        var addTax = (function () {
            return function (tax) {amount += amount*tax/100; return this.amount}
        })();

        addTax(20);
        console.log(this.amount);
###Excersise 05 Let's write a function to call GitHub API (https://api.github.com/users) and get users and return the users to the caller.

        const url = 'https://api.github.com/users';
        fetch(url)
            .then(response => response.json())
            .then(response => JSON.stringify(response))
            .then(data => {
                console.log(data);
                document.getElementById("demo").innerHTML = data;
            })
            .catch(error => console.error(error))
