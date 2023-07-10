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















