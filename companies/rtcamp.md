# What are Git and GitHub?

**Git**:
- Git is a version control system.
- It helps track changes in files.
- It is used mainly for coding projects.
- Git lets multiple people work on the same project without conflicts.
- It keeps a history of changes, so you can go back to an earlier version if needed.

**GitHub**:
- GitHub is a platform that uses Git.
- It is a website where you can host and share Git repositories.
- Developers use GitHub to collaborate on projects.
- It has extra features like issue tracking, project management, and code review.

# Difference between Git and GitHub

**Git**:
- Git is a tool.
- It is a version control system.
- It runs locally on your computer.
- Git manages and tracks changes in files.
- It allows you to revert to previous versions.

**GitHub**:
- GitHub is a service.
- It is an online platform that hosts Git repositories.
- It enables collaboration among developers.
- GitHub provides additional features like issue tracking, project management, and code review.
- It allows sharing and storing Git repositories on the cloud.

### Alternatives to GitHub

1. **GitLab**:
   - A web-based DevOps lifecycle tool.
   - Provides Git repository management, CI/CD, and project management.
   - Offers both cloud-hosted and self-hosted options.

2. **Bitbucket**:
   - A Git repository management solution by Atlassian.
   - Integrates well with other Atlassian products like Jira.
   - Offers cloud-hosted and self-hosted options.

3. **SourceForge**:
   - A web-based service that offers software developers a centralized online location to control and manage free and open-source software projects.
   - Supports Git, SVN, and Mercurial repositories.

4. **Azure Repos**:
   - Part of Microsoft Azure DevOps.
   - Provides Git repositories and TFVC (Team Foundation Version Control) for source control.
   - Integrated with other Azure DevOps services.

5. **AWS CodeCommit**:
   - A source control service hosted by Amazon Web Services.
   - Supports Git repositories.
   - Designed for secure and scalable management of source code.

# Cookies and Sessions

**Cookies**:
- Small pieces of data stored on the user's browser.
- Used to remember information about the user.
- Can store user preferences, login status, and tracking information.
- Set by websites and sent with each HTTP request to the server.
- Can have expiration dates; they can be temporary (session cookies) or permanent (persistent cookies).

**Sessions**:
- Server-side storage of user data.
- Used to keep track of user activity and state across multiple requests.
- Typically managed by assigning a unique session ID stored in a cookie on the user's browser.
- Data is stored on the server, not on the client.
- Usually temporary and expire when the user logs out or closes the browser.

**Difference between Cookies and Sessions**:
- **Storage Location**:
  - Cookies: Stored on the client-side (user's browser).
  - Sessions: Stored on the server-side.
- **Size Limit**:
  - Cookies: Limited in size (usually 4KB).
  - Sessions: No strict size limit; depends on server capacity.
- **Security**:
  - Cookies: Less secure; can be accessed and manipulated by users.
  - Sessions: More secure; data is stored on the server.
- **Expiration**:
  - Cookies: Can have long-term expiration dates.
  - Sessions: Typically expire when the user logs out or closes the browser.
- **Data Storage**:
  - Cookies: Can store simple data like preferences and tracking information.
  - Sessions: Can store more complex data since it is server-side.

# What is ReactJS and what happens when you change a state?

### ReactJS and State Changes

**ReactJS**:
- ReactJS is a JavaScript library.
- It is used for building user interfaces, especially single-page applications.
- Developed and maintained by Facebook.
- Allows developers to create reusable UI components.

**What happens when you change a state in ReactJS**:
1. **State Change**: You update the state of a component using the `setState` method or the `useState` hook.
2. **Re-render**: React triggers a re-render of the component that had its state changed.
3. **Virtual DOM**: React updates the Virtual DOM, a lightweight copy of the actual DOM.
4. **Diffing Algorithm**: React compares the updated Virtual DOM with the previous version to identify changes.
5. **DOM Update**: Only the changed parts of the actual DOM are updated, making the process efficient.

**Library or Framework**:
- ReactJS is a library, not a framework.
- It focuses on the view layer (UI) of an application.
- Unlike a framework, it does not include tools for handling routing, state management, or other aspects of application architecture, but it can be integrated with other libraries to manage those tasks.

# Components of ReactJS

**1. Functional Components**:
- Simple JavaScript functions.
- Receive props as an argument and return React elements.
- Use hooks for managing state and side effects.
- Example:
  ```javascript
  function Greeting(props) {
    return <h1>Hello, {props.name}!</h1>;
  }
  ```

**2. Class Components**:
- ES6 classes that extend `React.Component`.
- Have a render method that returns React elements.
- Can have state and lifecycle methods.
- Example:
  ```javascript
  class Greeting extends React.Component {
    render() {
      return <h1>Hello, {this.props.name}!</h1>;
    }
  }
  ```

**3. JSX (JavaScript XML)**:
- A syntax extension for JavaScript.
- Looks like HTML but can include JavaScript expressions.
- Used to describe the UI.
- Example:
  ```javascript
  const element = <h1>Hello, world!</h1>;
  ```

**4. Props (Properties)**:
- Read-only inputs to components.
- Passed from parent to child components.
- Used to pass data and event handlers.
- Example:
  ```javascript
  <Greeting name="Alice" />
  ```

**5. State**:
- Managed within the component.
- Used to store dynamic data and control the component's behavior.
- Can be updated with `setState` in class components or `useState` in functional components.
- Example (functional component):
  ```javascript
  const [count, setCount] = useState(0);
  ```

**6. Lifecycle Methods**:
- Special methods in class components that run at different stages of a component's life.
- Common methods include `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
- Example:
  ```javascript
  class Timer extends React.Component {
    componentDidMount() {
      this.timerID = setInterval(() => this.tick(), 1000);
    }

    componentWillUnmount() {
      clearInterval(this.timerID);
    }

    tick() {
      this.setState({
        date: new Date()
      });
    }

    render() {
      return <h2>It is {this.state.date.toLocaleTimeString()}.</h2>;
    }
  }
  ```

**7. Hooks**:
- Functions that let you use state and other React features in functional components.
- Common hooks include `useState`, `useEffect`, and `useContext`.
- Example:
  ```javascript
  import React, { useState, useEffect } from 'react';

  function Timer() {
    const [count, setCount] = useState(0);

    useEffect(() => {
      const timer = setInterval(() => setCount(count + 1), 1000);
      return () => clearInterval(timer);
    }, [count]);

    return <h1>{count}</h1>;
  }
  ```
