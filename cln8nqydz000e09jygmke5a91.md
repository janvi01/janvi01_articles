---
title: "HTML <div></div> vs. JSX <>...</> Syntax"
datePublished: Mon Oct 02 2023 08:57:37 GMT+0000 (Coordinated Universal Time)
cuid: cln8nqydz000e09jygmke5a91
slug: html-divdiv-vs-jsx-syntax
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694082627563/72f9d8d6-e0b2-4253-a4c0-28fb7305a453.png
tags: javascript, html5

---

If you've ever dived into the world of web design or writing HTML, or JavaScript code, you're likely familiar with the `<div></div>` tags. However, in recent years, a newcomer has emerged on the scene: the `<> </>` syntax. With its appearance, it may raise questions about how it differs from the trusty `<div></div>` duo. In this blog, let's explore the key distinctions between these two constructs and see when to use each one in your projects.

# **&lt;div&gt;&lt;/div&gt; - The HTML Container**

* `<div>` is a standard HTML element used for grouping and structuring content on a web page.
    
* **It is a block-level element, which means it creates a rectangular box on the web page that spans the full width of its parent container by default.**
    
* We can apply CSS styles to a `<div>` element to control its appearance and layout.
    
* It is commonly used to create divisions or containers for organizing and styling content.
    

```xml
<div>
  This is a div element that creates a rectangular box on the web.
</div>
```

![div illustration](https://cdn.hashnode.com/res/hashnode/image/upload/v1694081431848/d3baefa1-ec26-454f-a15e-0acd8f805cd9.png align="center")

# **&lt;&gt;...&lt;/&gt; - The JSX Fragment in JavaScript**

* The `<>...</>` syntax represents a JSX fragment in JavaScript. It is not a valid HTML element, but rather a way to group multiple elements.
    
* JSX fragments are often used in React applications to group elements without adding an unnecessary parent element to the DOM which can help avoid unnecessary nesting and DOM bloat, which can lead to improved performance by reducing the complexity of the rendered DOM tree.
    
* Fragments are not limited to divs, you can use them to group any combination of HTML elements or React components.
    
* The empty JSX tag `<></>` is shorthand for `<Fragment></Fragment>.`
    

Note: *You can inspect the DOM to verify that there are no wrapper elements around the &lt;Fragment/&gt; or empty &lt;&gt;&lt;/&gt; tags children:*

```xml
<>
  <p>This is a paragraph.</p>
  <button>Click me</button>
</>
```

### Benefits of using &lt;&gt;&lt;/&gt;

1. **Group and return multiple elements together**
    

A component can only return one element, but by using a Fragment you can group multiple elements together and then return them as a group.

```javascript
function App() {
  return (
    <>
      <Navbar />
      <Body />
      <Footer/>
    </>
  );
}
```

1. **Group elements along with text**
    

You can use `Fragment` to group text together with components.

```javascript
function DateRangePicker({ start, end }) {
  return (
    <>
      From
      <DatePicker date={start} />
      to
      <DatePicker date={end} />
    </>
  );
}
```

1. **Assign multiple elements to a variable**
    

You can assign empty tag elements to variables and pass them as props.

```javascript
function DialogBox() {
  const buttons = (
    <>
      <OKButton />
      <CancelButton />
    </>
  );
  return (
    <Dialog buttons={buttons}>
      Are you sure you want to leave this page?
    </Dialog>
  );
}
```

In summary, `<div></div>` is a standard HTML element for structuring content and creating containers, while `<>...</>` (or `<>...</>`) is a JSX fragment syntax used in React and similar frameworks to group elements without introducing an extra DOM element.

Thanks for reading! I hope you find this article useful. You can connect with me on [**Twitter**](https://twitter.com/janvibajo01).

*ref links -*

1. [*https://medium.com/fasal-engineering/what-are-react-fragments-or-the-react-empty-tags-190253582905*](https://medium.com/fasal-engineering/what-are-react-fragments-or-the-react-empty-tags-190253582905)
    

1. [*https://react.dev/*](https://react.dev/)