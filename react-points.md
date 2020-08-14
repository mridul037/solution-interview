Why is isMounted() an anti-pattern and what is the proper solution?
 
 ans)?
 
 2)Pointer Events provide a unified way of handling all input events. 
 The following event types are now available in React DOM:
<code>
onPointerDown
onPointerMove
onPointerUp
onPointerCancel
onGotPointerCapture
onLostPointerCapture
onPointerEnter
onPointerLeave
onPointerOver
onPointerOut
</code>
3)The component names should start with a uppercase letter but there are few exceptions on this convention. 
The lowercase tag names with a dot (property accessors) are still considered as valid component names.

<code>render(){
   return (
       <obj.component /> // `React.createElement(obj.component)`
      )
}</code>

4)It is recommended to avoid all uses of forceUpdate() ?

5)array of objects to a component with a particular shape then use React.PropTypes.shape() as an argument to React.PropTypes.arrayOf().

<code>ReactComponent.propTypes = {
  arrayWithShape: React.PropTypes.arrayOf(React.PropTypes.shape({
    color: React.PropTypes.string.isRequired,
    fontSize: React.PropTypes.number.isRequired
  })).isRequired
}</code>

6)What is the difference between setState() and replaceState() methods?
ans)  When you use setState() the current and previous states are merged. 
      replaceState() throws out the current state, and replaces it with only what you provide.

7)How to listen to state changes?  
(ans) componentDidUpdate(object prevProps, object prevState)

8)focus
ans)
  componentDidMount() {
    this.nameInput.focus()
  } 
   <input
          defaultValue={'Won\'t focus'}
    />
   <input
          ref={(input) => this.nameInput = input}
          defaultValue={'Will focus'}
    />
  
 9) React Transition Group and React Motion are popular animation packages in React ecosystem.
 
 10)React Router is a wrapper around the history library which handles interaction with the browser's window.
 history with its browser and hash histories. 
    
11)How to pass params to history.push method in React Router v4?

 ans) this.props.history.push    ({
      pathname: '/template',
      search: '?name=sudheer',
      state: { detail: response.data }   })
      
 12)The React Intl library makes internalization in React straightforward, with off-the-shelf components and an 
    API that can handle everything from formatting strings, dates, and numbers, to pluralization.
    React Intl is part of FormatJS which provides bindings to React via its components and API.     

13)Shallow rendering is useful for writing unit test cases in React. It lets you render 
  a component one level deep and assert facts about what its render method returns,
  without worrying about the behavior of child components, which are not instantiated or rendered.
  
14)mapStateToProps() is a utility which helps your component get updated state (which is updated by some other components):  
  const mapStateToProps = (state) => {
  return {
    todos: getVisibleTodos(state.todos, state.visibilityFilter)
  }
}
mapDispatchToProps() is a utility which will help your component to fire an action event (dispatching action which may cause change of application state):

const mapDispatchToProps = (dispatch) => {
  return {
    onTodoClick: (id) => {
      dispatch(toggleTodo(id))
    }
  }
}
15)How to access Redux store outside a component?
<code>store = createStore(myReducer)

export default store</code>

16)ajax call redux

export function fetchAccount(id) {
  return dispatch => {
    dispatch(setLoadingAccountState()) // Show a loading spinner
    fetch(`/account/${id}`, (response) => {
      dispatch(doneFetchingAccount()) // Hide loading spinner
      if (response.status === 200) {
        dispatch(setAccount(response.json)) // Use a normal function to set the received state
      } else {
        dispatch(someError)
      }
    })
  }
}

function setAccount(data) {
 return { type: 'SET_Account', data: data }
}


17)What is the proper way to access Redux store?
ans) Connect function

18)redux-saga is a library that aims to make side effects 
(asynchronous things like data fetching and impure things like accessing the browser cache)
in React/Redux applications easier and better.

19)What are the differences between call() and put() in redux-saga?

20)What is React memo function?
ans) Class components can be restricted from rendering when their input props are the same using PureComponent 
     or shouldComponentUpdate. Now you can do the same with function components by wrapping them in React.memo.
     
     <code>const MyComponent = React.memo(function MyComponent(props) {
 /* only rerenders if props change */
});</code>

21)link and navlink in react router
  When you navigate to a route using <Link>, history.push() is called, which adds an entry to the history stack. 
  
22)What are Keyed Fragments?
The Fragments declared with the explicit <React.Fragment> syntax may have keys. 
The general use case is mapping a collection to an array of fragments as below,  
