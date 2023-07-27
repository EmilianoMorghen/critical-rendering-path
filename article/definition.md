## Intro
// TODO - Write an actual intro

### What is Critical Rendering Path (CRP)?
Once the browser has downloaded the `html` document, it needs to render it into pixels so that we, as users, can enjoy a GUI. The steps that browsers take to render those pixels are called the **Critical Rendering Path**.

### Why should I care?
Well, loading, parsing, and rendering the documents are mandatory steps for the browser to display pixels on our screen, and this is why it's so important to understand the nuances of this process. Knowing how the browser renders those pixels gives us the chance to build more fluid and performant websites. On the other hand, even creating the smallest animation can be a tricky task and may result in a laggy experience.

It's probably common knowledge that online users continually raise their expectations when it comes to website loading time and fluidity. If our sites takes too much time to pop up or are laggy, they may very well choose to leave all togheter and click on our compotetitor's website.

So optimizing our softwares for CRP is a vital task that needs to be addressed.

## Process

### The Stages
Everytime we visit a website we trigger the CRP process. This process has 7 stages:
- Request
- Response
- DOM & loading external resources
- CSSOM
- Render Tree
- Layout
- Painting

Let's take a look at them in depth.

### The Stages

- **Request**
  This stage is triggered by the user, and explaining how the request reaches our servers is not in the scope of this article.

- **HTML Response**
  So our browsers are waiting for a response from the server, and the first bytes start incoming. This step actually has a big impact on the overall website performance. Caching and using the correct DNS are all valid strategies to optimize the time that the browser needs to wait for a resource.

- **DOM & Loading External Resources**
  This is where things start to get interesting. The browser starts to parse the HTML as soon as it receives the first bytes. 
  When the browser encounters an external resource, it immediately starts the requests to retrieve what we need. Some of them are blocking, such as fonts, HTML, CSS, and Javascript files. We will discuss later what strategies we have to reduce the number of blocking resources. 
  While parsing the document, the browser begins to create the Document Object Model, also known as DOM.

- **CSSOM**
  Less notorious but still critical for the first page render is the CSS Object Model. Once the DOM is ready, the browser starts to create the CSSOM. It is just a tree of style rules like colors, background, paddings, and all of the other rules that will style our page. 

- **Render Tree**
  With the DOM and the CSSOM ready, the browser starts to merge the two and creates the Render Tree, computing the style for all the visible components of the page. 

- **Layout**
  In this stage, values like sizes and coordinates of the elements will be calculated.

- **Painting**
  The final step that renders, or paints, the page on the screen.


