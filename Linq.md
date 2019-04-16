	1) LINQ - Language integrated query
	2) Linq providers:
	Convert linq to understandable format.
	Like linq to sql, linq to xml, linq to objects etc.
	3) Linq to sql file extension is .dbml
	4) Basically Linq will create context class.
	5) Query structure:
	**In case of database
	From student in dataContext.students
	Where student.gender='Male'
	Select students;
	
	**in case of objects
	Int[] numbers= {1,2,3,4,5,6}
	From number in numbers
	Where (number%2) ==0
	Select number;
	6) Linq query operator are implemented as extension methods on Ienumerable<t>
	7) Predicate are used in linq query 
	Where(student=>student.gender=="Male")
	8) Extension method:
	Where is implemented as an extension method.
	String strName ="Pragim";
	//lets change it to first letter as upper case.
	String result= strName.ChangeFirstLettercase();
	//Create helper class.
	//convert the string to char array and check the first char position and convert it to upper.
	
	To turn a method to extension method we have to do two things.
	-- first change the containing class to static.
	-- in the function signature, we must use this before the type of parameter.
	
	Extension method- definition
	** Extension method enables us to add methods to existing type without creating a derived type, 
	Recompiling or modifying the original type.
	They are special kind of static method and they are called as if they were instance method.
	9) Aggregate operator:
	int[] numbers= {1,2,3,4,5,6,7,8};
	//find the max using sql like
	int output = (from number in numbers
				select number).Max();
	Console.WriteLine(output);
	//find the min using linq
	int min = numbers.Min();
	Console.WriteLine(min);
	//find the min even number
	Console.WriteLine(numbers.Where(x=> x%2 ==0).Min());
	//find the sum of all the number
	Console.WriteLine(numbers.Sum());
	//find the sum of all off
	Console.WriteLine(numbers.Where(x=> x%2 != 0).Sum());
	//find the total number
	Console.WriteLine(numbers.Count());
	//Average
	Console.WriteLine(numbers.Average());
	
	10) Aggregate functions:
	
	string[] countries = {"India", "US", "UK", "Canada", "Australia" };
	//create the string of above countries seperated by comma.
	Console.WriteLine(countries.Aggregate((a,b) => a + ", "+b));
	
	//Find the product of all the items in array.
	int[] numbers = {2,3,4,5};
	Console.WriteLine(numbers.Aggregate((a,b) => a *b));
	//Aggregate pass the first two params of array to a and b and perform operation.
	
	11) Projection operator: select and selectMany
	.select(emp => emp.EmployeeID)
	The output will be Ienumerable.
	
	First name and gender using anonymous
	.select(emp => new {fristName= emp.firstName, Gender= emp.Gender});
	
