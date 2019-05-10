# Lesson plan
```
> Focus on having lots of in class exercises.


> DONT teach everything, let the students investigate topics on their own aswell!


> Focus on how to read documentation, google answers and google errors!!
```

To find examples of what teachers have taught before go to the class branches in the classwork folder, Fx [class 07](https://github.com/HackYourFuture-CPH/JavaScript/tree/class07/JavaScript1/Week1/classwork)

For exercises https://www.codewars.com is a good site.

---

- Arrays continued
    - Pop, push, shift, unshift
      - The longest of the word pairs unshift, push makes the array longer!
    - length
    - indexOf - Let the students investigate this
    - No map, filter or reduce
- Objects
    - Access properties two ways: .keyname and [keyname]
    - Key value
    - Array of objects
    - Let the students explain iterating an array of objects
    - Use real world examples (users, products, houselistings)
- [Code inspiration arrays and objects](#arrays-and-objects)
- [Codewar exercises](codewar-exercises)
- Call stack
  - Used for figuring code flow in js! Where does my function go when it is done here.
  - http://latentflip.com/loupe
  - [Exercise](#call-stack)

## Code inspiration

### Arrays and objects

```js
// one way to have multiple data about a student is with an array
// for each piece of data
const studentNames = [
  'Fowad',
  'Emil',
  'Zoey'
]

const studentAges = [
  32,
  25,
  28
]

console.log(studentNames)
console.log(studentAges)

// Another, more ergonomic way is with objects
const students = [
  { name: 'Fowad', age: 32 },
  { name: 'Emil', age: 25, teacher: true },
  { name: 'Zoey', age: 28 }
]

console.log(students)
// We can access properties with `.`
console.log(students[0].name)

// One object that we have seen before
const Math = {
  random: function () {
    return 42
  },
  round: function (x) {
  }
}


const person = {
  name: 'Emil',
  age: 25,
  role: 'Teacher',
  classes: ['Javascript 1', 'Javascript 2'],
  hobbies: {
    favourite: 'computers',
    sports: 'running to class'
  }
}

console.log(person)

// Add new property
person.lastname = 'Bay'

console.log(person)

delete person.lastname

console.log(person)

console.log(person.hobbies.favourite)
console.log({ favourite: 'computers', sports: 'running to class' }.favourite)

'Hello world'.replace('Hello', 'Hej').replace('world', 'verden')

function graduatedClass (student, className) {
  if (student.classes.includes(className)) return 'Error'

  student.classes.push(className)
}

console.log(person)
graduatedClass(person, 'HTML')
console.log(person)
graduatedClass(person, 'HTML')

const newPerson = {
  name: '',
  age: ''
}

function addStudent(student) {
  if (student.name == null && typeof student.name === 'string') return 'Error'
  if (student.age == null) return 'Error'

  students.push(student)
}

addStudent({ name: 'Rahim' })
console.log(students)

// ways to access properties

person.name
person['name']

const prop = 'name'
person[prop]

person['name'] = 'Maria'
person[0] = 'Hello world'

console.log(person)

function pick (obj, prop, defaultValue) {
  if (obj[prop]) return obj[prop]

  return defaultValue
}

pick(person, 'age', 'Unknown')
```

### Call stack
```js
function a() {
    // add to call stack
    b();

    return 'a';
    // remove from call stack
}


function b() {
    //throw 'hello';
    return 'b';
}

a();


```


## Exercises

## Call stack

Draw the call stack array at every draw point
```js
function bookPlaneTickets() {
    // draw
    console.log('Plane tickets booked');
    requestVacationDays();
    // draw
}

 function bookHotel() {
    console.log('Hotel booked');
    // draw
    planItinerary();
    // draw
}

function requestVacationDays() {
    // draw
    console.log('Vacation days requested');
    // draw
}

function planItinerary() {
    console.log('Itinerary done');
    // draw
}

function planTrip() {
    bookPlaneTickets();
    // draw
    bookHotel();
    // draw
    console.log('Trip planned');
}
// draw
planTrip();
// draw
```

### Codewar exercises
- [CodeWars - Add property to every object](https://www.codewars.com/kata/add-property-to-every-object-in-array/train/javascript)
- [CodeWars - Job Matching 1](https://www.codewars.com/kata/job-matching-number-1/train/javascript)
- [CodeWars - Who's Online](https://www.codewars.com/kata/whos-online/train/javascript)
- [CodeWars - Ironman Triathlon](https://www.codewars.com/kata/ironman-triathlon/train/javascript)
- [CodeWars - Job Matching 2](https://www.codewars.com/kata/job-matching-number-2/train/javascript)
- [CodeWars - Color Association](https://www.codewars.com/kata/colour-association/train/javascript)
- [CodeWars - Unfinished loop](https://www.codewars.com/kata/unfinished-loop-bug-fixing-number-1/train/javascript)
- [CodeWars - Is this my tail](https://www.codewars.com/kata/is-this-my-tail/train/javascript)
- [CodeWars - Longest word](https://www.codewars.com/kata/squash-the-bugs/train/javascript)
- BONUS [CodeWars - Super Duper Easy](https://www.codewars.com/kata/super-duper-easy/train/javascript)