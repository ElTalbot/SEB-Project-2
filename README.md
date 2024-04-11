# General Assembly

### Project 2 (Disney Character Board)

Our Disney Characters API provides the user with the opportunity to browse a list of Disney Character Cards.

Each Character Card is a clickable element that if selected provides the user with a more detailed character bio - all of which is rendered from our chosen API ‘INSERT DISNEY API’  
The addition of a search bar and drop-down offers the user the ability to tailor their experience and retrieve a more refined result.

## Concept

A user friendly, simple platform providing the user with key information around a vast array of Disney Characters - be it a general overview or a more detailed bio.

## Game Link

[Disney Character Board](https://seb-78project2.netlify.app/character/18)

## Technology Used

### React(JSX)

React was used to render and visually display the data fetched from the API. In this instance was the Disney Characters:

- Name
- ID
- ImageUrl
- Films
- TvShows
- SourceUrl

### Insomnia

Insomnia was used to decipher the effectiveness of the API and to make sure that the data pulled in from the Disney API wasn’t broken and could be fetched and displayed with ease.

![Insomnia Request for the Disney API](<src/README Assets/Screenshot 2024-03-08 at 21.51.41.png>)

### Figma

Figma was used to wireframe the design of our character board as well as define the potential user journeys.
We also used Figma to pseudocode the potential functions, event listeners and array methods that may be required to build our MVP.

![Figma Wireframes](<src/README Assets/Figma.png>)

### GitHub

Setting up individual branches from our newly created GitHub repository meant both my partner and I were able to collaboratively build the project.

### Bulma

The integration of Bulma in React meant we were able to utilise this styling framework to build our project

## Time Frame

This was a collaborative paired project that was to be completed in 2 days. It was a project designed to consolidate everything we have learned about React and APIs

## Instructional Team Brief

The brief given to us by the instructors can be seen in the README below - we were given a decent scope to explore potential APIs and how we could utilise our findings within a project. However, a sign off was required to make sure we decided on an appropriate, achievable MVP.

![Figma Wireframes](<src/README Assets/README Brief 1.png>)

![Figma Wireframes](<src/README Assets/README Brief 2.png>)

## Planning, Process and Implementation

### Research

The initial brief as seen below outlines the deliverables, challenges and suggested ways to start the project.

Prior to collaborating we were given the opportunity to research potential APIs and using both Insomnia and VS Code to consolidate the API and make sure the data could be effectively fetched and used.
This also gave us the chance to think about ideas for the project and how best to use the API.

## Planning

### Collaboration

On being assigned a partner we were given time to discuss each others research and to finalise our project idea - both my partner and I seemed to be on a similar wavelength. My partner proposed the idea of a character board and from looking at a variety of APIs I suggested the idea of it being a Disney Character Board.

Following a more in depth collaborative research and discussion around the Disney API we decided to settle on the Disney board idea.

### Pseudocode

Our next step was to pseudocode the look, feel and function of our minimal viable product(MVP).
This also gave us the opportunity to discuss the potential in-app React elements, functions, Array methods and event listeners required to build our MVP

![Figma Pseudocode](<src/README Assets/Figma Psuedocode.png>)

### Initial Build

#### <ins>First Step - Components and Routers</ins>

Using the layout of the design as a guide we created a new component for each part of the character board - these components would hold the code that would define the functions they perform.

![Components folder](<src/README Assets/Components.png>)

It was then important to make sure that each component could be navigated to and data could be translated and passed between which was made possible by the "react-router-dom" - by importing the individual components into the App.tsx, the path to that component could be defined (see below for examples of importing components and using the Router tool)

![Routes and navigation](<src/README Assets/Routes.png>)

#### <ins>Second Step - API</ins>

To fetch the data from the Disney API we used the `React.useState()` hook (as seen below) this sets the state of the `character` variable whenever the setter function is called.

![useState Hook](<src/README Assets/useState.png>)

`React.useEffect()` was the hook used to call the `async function fetchCharacter` (as seen below) on page load which in turn pulls through the first 200 results of our Disney API.
This function fetches the data from the API and declares a variable `resp` to gold the data returned by the API call.
`resp.json()` returns a promise that converts the JavaScript string into a JavaScript object representation of the data, making it readable and usable.
Finally, `setCharacter(characterData)` uses the `setCharacters` function previously defined to update the state variable `character` (as defined in the `useState()` hook ) with the fetched character data.

![useEffect hook](<src/README Assets/useEffect.png>)

#### <ins>Third Step - Character List (.map)</ins>

After fetching the data, we used a `.map` method to iterate through the `character` array holding the recently fetched data of characters called from the Disney API and `return` a new array of the desired elements as defined (see screenshot below). The `Character` component seen here is rendered with various props that are then passed to the `Character` component to render specific information about each character which are then displayed.

![.map through an array](<src/README Assets/map.png>)

### Challenges

A number of challenges arose throughout this project, on clicking on one of the character cards our plan was for this to display a more detailed bio of each character. The main hurdle here was retrieving data that sat inside of an array inside of an object inside of an array.
The initial data displayed included name, id and image all of which were strings which when fetched displayed using the aforementioned method. However due to the films and tv shows being inside of another array when calling the API we needed to use the `.map` method again to iterate through the specific film and tvShow arrays to access this data and be able to display it onto the card.

In addition to the card needed to display the specific data associated with the character card clicked on the `CharacterList` page - this became problematic.
In order to achieve this (as seen below) we carried out another fetch request that runs when the page loads (which only occurs when the aforementioned character card is clicked). However, the difference being we used the `id` of the character data to pass through the right information associated with the character clicked on.

![Show character bio](<src/README Assets/Show character.png>)

### Bulma

Being a new user of Bulma was a stumbling block during this project, it is a really useful CSS framework that once mastered can be extremely beneficial however, due to my lack of experience I felt that the use of Bulma meant the time spent on additional features was limited. On reflection, I may have resorted to basic CSS so that other features could have been focussed on - and I could have independently worked on gaining experience with Bulma and used it in projects further down the line.

## Key Learnings and Takeaways

### User Journeys

Defining initial user journeys was useful in navigating the start of the project and helped guide us in building the MVP, making sure that the users were taken into consideration.

However, later challenges as mentioned previously highlighted the need for a more thorough breakdown of user journey's to help mitigate the chance of bugs and uncaught UI/UX issues.

### Collaboration

Being our first collaborative project it was important that both of us were on the same page and understood the expectations of our role in the team.

Having never coded alongside others, our instructor gave us a brief introduction into the format of having a driver and navigator and the importance of rotating these roles on a regular basis.
My key learning here although needs more attention and practice is within git and how to create branches, merge and resolve potential conflicts within our code in order to share.

Although we successfully completed our project, our collaboration followed mainly the driver, navigator format of pair programming. On reflection, incorporating independent feature branches to allow for both solo and paired programming would have given us more experience with merging and conflict resolution in git.

### Asking For Help

As a collaborative project, this experience has highlighted the importance of support and having the confidence to ask for help as well as having your own voice - facing a challenge and working together to find the solution is incredibly important.

When faced with a challenge or bug in the code whether independent or collab it can be useful to help see things from a different perspective. Asking for the support of instructors or even other peers not engrossed in the code and learning from them is important.

## Bugs

### Search bar and Dropdown

The main 2 additional features we included within our project was a search bar and a dropdown. The idea was for the search bar to allow the user to filter by name and the dropdown to enable the user to pick a film and see all characters in that film.

#### Search bar

The addition of the search bar alone was achieved by a `React.useState()` hook,

![Show character bio](<src/README Assets/SearchState.png>)

the event of a user typing in the input field calls the `handleChange` function that sets the `search` variable to the value within the input.

![Show character bio](<src/README Assets/handleChange.png>)

This then calls the `filterCharacters()` function that return the character data that `includes()` the value in the search bar.

#### Dropdown

The addition of the dropdown followed a similar process, using a `React.useState()` hook
and the event of the value within the dropdown changing meant the `function handleChangeFilm()` was called and the value was updated and set to the current value in the dropdown.

![Show character bio](<src/README Assets/handleChangeFilm.png>)

The idea was for this to then in turn map through the hard coded data values we predefined and pull in the character that matched the value in the dropdown,

![mapping through films](<src/README Assets/Film map.png>)

![Hardcoded films](<src/README Assets/films.png>)

however, the problem was we were trying to call 2 `useEffect()` hooks that caused an error.

![Show character bio](<src/README Assets/2 useEffect.png>)

To mitigate this, we added an argument to the hook (see below) enabling us to define when this hook was called and in this case it was only called when the selectedFilm `value` in the dropdown changed.

![Show character bio](<src/README Assets/2 useEffect argument.png>)

#### Feature Interaction

The interaction between the search bar and dropdown came into question on reviewing the potential user journeys

These in particular ..

<ins>As a user I want .. </ins>

1. Search characters from the search bar
2. Search for characters in a specific film using drop-down
3. Search through characters within the film selected in the drop-down
4. Be able to Return to searching the whole data set after searching through a film

In order for the user to use the search bar to search the characters in the film selected in the dropdown we needed the 2 features to interact and for the characters to filter depending on both `handleChange` functions. To do this we used the && and || operators (see below)

The `filterCharacters()` function filters the characters data based on the search criteria provided through the `search` and `value` variables.

The `filter()` method creates a new array containing the elements that fit the criteria of the implemented callback function - in this case the call back function checks for 2 conditions:

1. `search === "" || character.name.toLowerCase().includes(search.toLowerCase())` - this is checking if the `search` variable is empty or if the characters name contains the search string. If `search` is empty, then all characters are considered a match therefore, all the characters will be displayed. Otherwise, only the characters whose names contain the search string are considered a match and displayed.
2. `value === "" || character.films.includes(value)` - this is checking whether the `value` variable is empty or if the films array contains the `value`. If the value is empty, all characters are considered a match, otherwise only characters whose films array includes the `value` are considered a match and displayed.

The interaction comes with the addition of the `&&` operator, this means that if a user selects a specific film the `value` will never be empty therefore, the `filterCharacters()` function will always return characters with the selected film in their film array. This effectively allows the user to use the search bar to search the characters based on the selected film `value`.

![Search by search bar and dropdown](<src/README Assets/&&.png>)

#### Empty Search Value

Another bug was the problem that arose when the user selected a film, as without the option to select an empty value the filtered return will always be associated with the dropdown film value and the user will never be able to return to the general search function.
To prevent this from happening we added the option to select an empty value.

## Future Improvements

I believe with every project there is always something to learn and to improve on. Learning along the way and feedback from my partner, instructors and other peers is how I hope projects such as these can progress and develop with time.

This project in particular, the future improvements at the forefront of my mind include:

1. Favourites - the opportunity for the user to select their favourite disney character and for them to build a little team of favourites would have been an added feature that could have created a more interactive board
2. Additional Search Features - the film drop down and search bar gives the user greater scope in finding their desired disney character. Being able to carry out a more detailed filter the user would experience a more UX friendly interface
3. Additional APIs - The Disney API we used to fetch the character data was limited with its supply of data available and with more time it would have been useful to search for different API’s that may have provided us with more information. With more information the scope of the character board would have been greater and therefore more useful to the user.
4. Styling - the aesthetics and layout is an incredibly important part of the project, the combination of the UI and UX is key to creating a platform most suited to the user, and therefore, making it more user-friendly.
   In this project I believe managing time better and prioritising each aspect of the process as well as assigning roles and responsibilities effectively may have resulted in a more professional and engaging look.
