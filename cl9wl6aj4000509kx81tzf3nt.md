---
title: "active NavLinks using React router"
seoTitle: "Creating Active NavLinks with React Router: A Step-by-Step Tutorial"
datePublished: Mon Oct 31 2022 09:36:10 GMT+0000 (Coordinated Universal Time)
cuid: cl9wl6aj4000509kx81tzf3nt
slug: active-navlinks-using-react-router
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1667201000933/EbMyYCr2i.png
tags: reactjs, blogswithcc

---

Hello everyone. Welcome to this tutorial on how to create active NavLinks using **React Router**.  
  
Navbars are a common feature in web applications, providing users with easy access to different pages or links. In this tutorial, we'll show you how to style your navbar to look great and improve usability by highlighting the active link when a user is browsing a specific page. With the help of **React Router's NavLink component**, this can be done easily and with minimal code. Follow along to learn how to implement this feature in your own React projects.

> How about incorporating a navigation link highlighting feature that activates when a user navigates to a particular webpage?

Just like the one shown below -

![video](https://media.giphy.com/media/yYMeFfbPMmZe7nus0l/giphy.gif align="center")

![Screenshot 2022-10-29 at 1.36.08 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1667030796940/rcki2Kk8C.png align="left")

Believe it or not, it can be easily done with ease using `react-router NavLink`.

So, let's jump right into the tutorial on how to do that...

`NavLink` is a special kind of Link in react-router that tells you if a link is active or not.

* First, set up your project using `react` and `react-router`. React router has been updated to its new version, check out the [documentation](https://reactrouter.com/en/v6.3.0/getting-started/overview) to know more.
    
* Let's create some basic routes for our project like homepage, about, contact, etc. You can choose as many as you like. For this tutorial, we will make a homepage, an about page, and a contact page. Open your app.js file and make the changes in the code as shown below:
    

```javascript
import "./App.css";
import { Route, Routes } from "react-router-dom";
import About from "./About";
import Contact from "./Contact";
import Home from "./Home";

function App() {
  return (
    <div className="App">
      <Routes>
        <Route path="/home" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </div>
  );
}

export default App;
```

* Make sure to create separate file components for different routes like About, and Contact.
    
* Add NavLink wherever you want to display your navbar. We have two methods to style our Link when it is active.
    

> using `style`  
> using `className`

You can pass a function to either `style` or `className` to customize the inline styling or change the class name based on the component's active state.

Let's do it using style...

```javascript
<div className="nav">
        <NavLink
          to="home"
          style={({ isActive }) => ({
            backgroundColor: isActive ? "blue" : "black",
          })}
          className="navitem"
        >
          Home
        </NavLink>
        <NavLink
          to="about"
          style={({ isActive }) => ({
            backgroundColor: isActive ? "blue" : "black",
          })}
          className="navitem"
        >
          About
        </NavLink>
        <NavLink
          to="contact"
          style={({ isActive }) => ({
            backgroundColor: isActive ? "blue" : "black",
          })}
          className="navitem"
        >
          Contact
        </NavLink>
      </div>
```

Adding a little styling to your navbar...

```javascript
.nav {
  display: flex;
  justify-content: space-around;
}
.navitem {
  text-decoration: none;
  background-color: #000;
  color: #fff;
  padding: 10px 20px;
  font-weight: bold;
}
```

Similarly, you can do it using className, creating a separate class for the link when it is active. It is preferable when you want to change more than one CSS property.

Example:

```javascript
<NavLink to="about"
          className={({ isActive }) => 
              (isActive ? "activeclassName" : "className")}
        >
          About
        </NavLink>
```

Run your project and refresh the local host to see the changes. Check out the source code repo here - https://github.com/janvi01/navlink-demo.

This can also be done using react `useLocation` [hooks](https://reactjs.org/docs/hooks-intro.html).

Thanks for reading! Please check out my other blog posts [here](https://janvi01.hashnode.dev/).

You can connect with me on [Twitter](https://twitter.com/janvibajo01) or [LinkedIn](https://www.linkedin.com/in/janvi01/).