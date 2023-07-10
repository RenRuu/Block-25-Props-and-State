# Block-25-Props-and-State

What is the purpose of the useState hook?
    - Google: allows you to have state variables in functional components
    - Basically useState is the ability to encapsulate local state in a functional component.

State management is a very important paradigm to understand in Web Development.
    - Popular libraries to handle state management with React including Redux, Mob-x.
    - Understanding various techniques to pass data around out React applications will help build clean and efficient user interfaces.

    Ref: https://react.dev/learn/passing-props-to-a-component 

        Review: State
            Can add state values to components with the useState hook
        
    Stage 1:
                function App () {
            const [user, setUser] = useState ({});

            return (
                <div>
                    <p> Welcome {user.name} </p>
                </div>
            );
        }

    Stage 2:
                function App () {
            const [user, setUser] = useState ({});

            return (
                <div>
                    <p> Welcome {user.name} </p>
                    <Profile/> //this component needs the user data
                </div>
            );
        }

        Above, we have an App component, with a user object stored in state.
            If the state value from one component needs to be shared throughout our application = Props

        Props
            - React components use "props" to share information with each other.
            - Parent components can pass information to child components by giving them "props".
            - Props are visually similar to HTML attributes and we have actually observed some so far already, such as "className","src","alt", ect... 
            - We can pass ANY value through them, such as objects, arrays, and functions.

    Stage 3:
                function App () {
            const [user, setUser] = useState ({name: "Shelly", age: 35});

            return (
                <div>
                    <p> Welcome {user.name} </p>
                    <Profile user={user} size={300} imageUrl="/images/profile.jpg" /> 
                </div>
            );
        }

        We have now passed some data into the <Profile> Component.  Plus two new "Props" were made "imageUrl, size".

            Inside of our Profile component, those props we passed are now available 

                function Profile ({user, size, imageUrl}) {
                    //user, size, and imageUrl are now all accessible
        }

            Functional React components take only one argument, a props object. To access each individual prop passed in, we would have to reach into the props object and say " props.user props.size props.imageUrl

                function Profile (props) {
                    //....
        }

        As we generally do not need the whole props object, we can use "object deconstruction" to save ourselves time. Can then use those values where we need in our component.

    Stage 4:
                function Profile ({user, size, imageUrl}) {
            return (
                <div> 
                    <p>
                        Hello my name is {user.name} and I am {user.age} years old.
                    </p>
                    <img src={imageUrl} alt="profile image" height={size} width={size} />
                </div>
            );
        }

----------------------------------------

ref: https://www.youtube.com/watch?v=IYvD9oBCuJI 

Props - arguments to a function 
    when you create a component inside of react and you want to render it. You're going to pass it the props that you want to give to it.

    Example 
        We have a counter application
            Thing your most likely going to pass to that counter is the initial count. Essentially what your count should start at.
            
            So your going to pass your counter component it's initial count inside of the props. The reason we are using the props like this is because props is kind of for things that you pass to a function. 

            There what you want to initialize your component to or what you want your component to render like. We want our initial count to be zero so we're gonna pass that through in the props.

State - something inside of a component 

Big difference between props and state is:
- state is handled in the component and you can update it inside the component (inside of the component)
    *If you change state your application will re-rended the section
    *Stores information and changes it 
- props are handled outside the component and must be updated outside of the component (pass into a component)
    *Displays information inside of a component without hard coding it 

Essentially, it's a variable to a function or when you create a class with a constructor. The things you pass to the constructor of that class are going to be the things that are your props for a component in react.


State 
    Page has title and description > but changes when you select something > stores the data and updates to the new details 

Props
    Page has title and description > information passes down from the parent and doesn't change inside the component

















