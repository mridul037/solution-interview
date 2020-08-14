Why is isMounted() an anti-pattern and what is the proper solution?
 
 ans)?
 
 2)Pointer Events provide a unified way of handling all input events. 
 The following event types are now available in React DOM:

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

3)The component names should start with a uppercase letter but there are few exceptions on this convention. 
The lowercase tag names with a dot (property accessors) are still considered as valid component names.

render(){
   return (
       <obj.component /> // `React.createElement(obj.component)`
      )
}

4)It is recommended to avoid all uses of forceUpdate() ?

5)array of objects to a component with a particular shape then use React.PropTypes.shape() as an argument to React.PropTypes.arrayOf().

ReactComponent.propTypes = {
  arrayWithShape: React.PropTypes.arrayOf(React.PropTypes.shape({
    color: React.PropTypes.string.isRequired,
    fontSize: React.PropTypes.number.isRequired
  })).isRequired
}
6)
