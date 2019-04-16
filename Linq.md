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
	
	12) SelectMany:-
	//SQL Like
	From s in strArray
	From c in s
	Select c;
	
	//With Linq
	.SelectMany(s=> s);
	
	13) Difference b/w select and selectMany
	Select many will flatten the lists to one list.
	Select will return list of list.
	
	14) Ordering operator in Linq:
	OrderBy or OrderByDescending works well if we need to sort a collection just by one value or expression.
	--OrderBy(s=>s.name);
	--OrderByDescending(s=>s.name);
	
	ThenBy and ThenByDescending works well if we have multiple expression.
	
	-- OrderBy(s=>s.mark).ThenBy(s=>s.Name).ThenBy(s=>s.StudenId);
	--OrderBy(s=>s.mark).ThenBy(s=>s.Name).ThenByDescending(s=>s.StudenId);
	-- reverse will just reverse the items in the list.
	
	15) Partitioning operator:
	-- Take
	String[] countries = {"Australia","Canada","Germany","US", "India"};
	Countries.take(3)
	Output-- "Australia", "Canada","Germany"
	--Skip
	Skip the specified number of elements
	Countries.skip(3)
	Output--"US", "India"
	--TakeWhile
		-- Return countries starting from the beginning of the array until a country name 
		Is hit that does not have length greater than 2 chars.
	Countries.TakeWhile(s=>s.length>2);
	Output: "Australia", "Canada","Germany"
	--SkipWhile
	Countries.TakeWhile(s=>s.length>2);
	Output: "US", "India"
	
	16) Paging: 
	It can be implemented using skip and take operator.
	
	17) Deferred execution or greedy execution:
	//The query executed when we iterate over the result object and not when we declare the query.
	Select, Where, take, skip are lazy operators
	//Greedy operators.
	Count, Average, min, max, ToList are greedy operators.
	
	18) Conversion Operator:
	ToList, ToArray,ToDictonary, ToLookup
	Cast,offtype,AsEnumerable,AsQueryable
	
	
	ToLookUp creates a lookup, it's like a dictionary, a look up can contain duplicate keys whereas a dictionary cannot.
	This is kind of a group by.
	
	19) Cast and oftype:
	Cast - convert all the items within an existing collection to another type and return them in new collection. It is used for differed execution. If casting fails, an exception will be thrown and it will throw when we are iterating over results.
	
	OfType: It will not fail while casting if types does not match. It will discard others and give us the desired types.
	
	20) AsEnumerable and AsQuerable:
	
	AsEnumerable breaks the LINQ to two parts. The inside part (This is executed as LINQ to SQL)and outside part(executed as LINQ to objects).
	This is used to move query execution to the client side.
	
	21) GroupBy operator
	It belongs to grouping operator category. The output is (Igrouping<k,v).
	The output is of dictionary type.
	
	
	
	
	
	
	
	


