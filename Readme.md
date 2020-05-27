React APT :
https://www.youtube.com/watch?v=N0Th97UwR7I

to install Reac>
npm install -g create-react-app


to create add
> cd path of folder
>create-react-app "myapp" <name of application>

after installing all dependencies
go to in app
cmd> npm start or yarn start

then it will run on browser
>http://localhost:3000
>http://127.168.0.107:3000


also install react developer tool> react chrome extension
https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en



here,
from src/App.js 
there is a App function

so, created new function header and footer
function Footer(){
  return(
    <h1>Welcome to Footer</h1>
  );
}

function Header(){
  return(
    <h1>Welcome to Header</h1>
  );
}


and call into the App with div tag

function App() {
  return (
    <div>
      <Header />
    <h1>Welcome to React</h1>
      <Footer />
    </div>
  );
}
-------------
Class component 

here,
from src/App.js 

class App extends React.Component{
  render(){
    return("Hello")
  }
}

--for return multiple value
class App extends React.Component{
  render(){
    return(
      <div>
        <h1>H1</h1>
        <h2>H2</h2>
      </div>
    )
  }
}


-- for component and Properties
https://reactjs.org/docs/components-and-props.html

here,
from src/App.js 

class App extends React.Component{
  render(){
    return(
      <div>
        <h1>H1</h1>
        {this.props.firstName}
      </div>
    )
  }
}

and --
In src/index

ReactDOM.render(
  <React.StrictMode>
    <App firstName='Jigar'/>
  </React.StrictMode>,
  document.getElementById('root')
);


--for state
https://reactjs.org/docs/state-and-lifecycle.html

class App extends React.Component{
    constructor(){
    super();
    this.state = {
      demo1 : "One",
      demo2 : "Two"
    }
  }

  render(){
    return(
      <div>
        <h2>{this.state.demo1}</h2>
        <h2>{this.state.demo2}</h2>
        </div>
    )
  }
}


------
class App extends React.Component{
  constructor(){
  super();
  this.state = {
   count : 0
  }
}

btnClick(){
  this.setState({
    count:this.state.count + 1
  })
}

render(){
  return(
    <div>
      <button onClick={this.btnClick.bind(this)}>Click Me</button>
      <h1>Value is {this.state.count}</h1>
    </div>
  )
}
}







----
Conditional Rendering
-
for navigation
react-router-dom
https://www.npmjs.com/package/react-router-dom

>npm i react-router-dom --save

create to pages Home and About

import React from 'react';

class About extends React.Component{
    render(){
        return(<div>
            <h1>About</h1>
            </div>
        )
    }
}

export default About;

import React from 'react';

class Home extends React.Component{
    render(){
        return(<div>
            <h1>Home</h1>
            </div>
        )
    }
}

export default Home;


--
App.js
--class App extends React.Component{
  constructor(){
  super();
  this.state = {
   count : 0
  }
}

btnClick(){
  this.setState({
    count:this.state.count + 1
  })
}

render(){
  return(
    <div>
    <Router>
      
        <ul>
          <li>
            <Link to={'/'}>Home</Link>
          </li>

          <li>
            <Link to={'/about'}>About</Link>
          </li>

          </ul>
          
          <switch>
            <Route exact path = '/' component={Home} />
            <Route exact path = '/about' component={About} />
            </switch>

      </Router>
    
      <button onClick={this.btnClick.bind(this)}>Click Me</button>
      <h1>Value is {this.state.count}</h1>
    </div>
  )
}
}

------
axios - load json api


