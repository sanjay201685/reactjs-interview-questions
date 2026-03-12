# Reactjs interview questions



For \*\*5 years of React experience\*\*, interviewers usually test \*\*core React knowledge, performance optimization, architecture decisions, and real-world problem solving\*\*. Below are \*\*common React interview questions with short guidance\*\*.



\---



\# 1. Core React Questions



\### 1. What is React?



React is a \*\*JavaScript library for building user interfaces\*\*, especially \*\*single-page applications (SPA)\*\*. It uses \*\*component-based architecture\*\* and a \*\*virtual DOM\*\* to improve performance.



\---



\### 2. What is Virtual DOM?



The \*\*Virtual DOM\*\* is a lightweight copy of the real DOM.



Process:



1\. React creates Virtual DOM.

2\. When state changes, React creates a new Virtual DOM.

3\. React compares old vs new DOM (\*\*diffing\*\*).

4\. Only the changed parts are updated in the real DOM.



Benefit: \*\*Improves performance\*\*.



\---



\### 3. What are React Hooks?



Hooks allow functional components to use \*\*state and lifecycle features\*\*.



Common hooks:



\* `useState`

\* `useEffect`

\* `useContext`

\* `useMemo`

\* `useCallback`

\* `useRef`



Example:



```javascript

const \[count, setCount] = useState(0);

```



\---



\### 4. Difference between useEffect and useLayoutEffect



| useEffect            | useLayoutEffect           |

| -------------------- | ------------------------- |

| Runs after DOM paint | Runs before DOM paint     |

| Non-blocking         | Blocking                  |

| Used for API calls   | Used for DOM measurements |



\---



\### 5. What is JSX?



JSX is \*\*JavaScript XML syntax\*\* used in React to write HTML inside JavaScript.



Example:



```javascript

const element = <h1>Hello World</h1>;

```



JSX gets converted into `React.createElement()`.



\---



\# 2. Component \& State Management



\### 6. Difference between State and Props



| State                    | Props              |

| ------------------------ | ------------------ |

| Mutable                  | Immutable          |

| Managed inside component | Passed from parent |

| Can change               | Read-only          |



\---



\### 7. Controlled vs Uncontrolled Components



\*\*Controlled\*\*



\* React controls form state.



```javascript

<input value={name} onChange={(e)=>setName(e.target.value)} />

```



\*\*Uncontrolled\*\*



\* DOM controls the state using `ref`.



\---



\### 8. What is lifting state up?



Moving shared state to the \*\*closest common parent\*\*.



Example:

Two components need same data → move state to parent.



\---



\# 3. Performance Optimization



\### 9. What is React.memo?



Used to \*\*prevent unnecessary re-rendering\*\*.



```javascript

export default React.memo(MyComponent);

```



Component re-renders only if props change.



\---



\### 10. useMemo vs useCallback



| useMemo         | useCallback        |

| --------------- | ------------------ |

| Memoizes values | Memoizes functions |



Example:



```javascript

const memoValue = useMemo(()=>expensiveCalc(a,b),\[a,b])

```



```javascript

const memoFunc = useCallback(()=>handleClick(),\[])

```



\---



\### 11. What is code splitting?



Splitting JS bundle into smaller parts.



Used with:



```javascript

const Home = React.lazy(()=>import('./Home'))

```



with `Suspense`.



Benefit: \*\*Faster loading\*\*.



\---



\# 4. React Architecture Questions



\### 12. What is Context API?



Used to share data \*\*without prop drilling\*\*.



Example:



```javascript

const UserContext = createContext();

```



Used with:



```

Provider

useContext

```



\---



\### 13. Redux vs Context API



| Redux                    | Context             |

| ------------------------ | ------------------- |

| Complex state management | Simple global state |

| Middleware support       | No middleware       |

| Large apps               | Small/medium apps   |



\---



\### 14. What are Higher Order Components (HOC)?



A function that takes a component and returns a new component.



Example:



```javascript

const withAuth = (Component)=>{

&#x20;return function(){

&#x20;  return <Component />

&#x20;}

}

```



\---



\### 15. What are Custom Hooks?



Reusable logic using hooks.



Example:



```javascript

function useFetch(url){

&#x20;const \[data,setData] = useState(null);

}

```



\---



\# 5. React Router Questions



\### 16. What is React Router?



Library used for \*\*navigation in SPA\*\*.



Main components:



\* `BrowserRouter`

\* `Route`

\* `Link`

\* `useNavigate`



\---



Example:



```javascript

<Route path="/about" element={<About />} />

```



\---



\# 6. Advanced Questions



\### 17. What is reconciliation in React?



Process React uses to \*\*compare old and new virtual DOM\*\* and update real DOM efficiently.



\---



\### 18. What are keys in React lists?



Keys help React identify \*\*which items changed, added, or removed\*\*.



Example:



```javascript

items.map(item => <li key={item.id}>{item.name}</li>)

```



\---



\### 19. What is SSR?



\*\*Server Side Rendering\*\* renders React on the server.



Benefits:



\* Better SEO

\* Faster first load



Framework used: \*\*Next.js\*\*



\---



\### 20. What is hydration?



Process of attaching React event listeners to \*\*SSR rendered HTML\*\*.



\---



\# 7. Coding Questions (Very Common)



\### Debounce in React



```javascript

function debounce(fn, delay){

&#x20;let timer;

&#x20;return (...args)=>{

&#x20;  clearTimeout(timer)

&#x20;  timer = setTimeout(()=>fn(...args),delay)

&#x20;}

}

```



\---



\### Fetch API example



```javascript

useEffect(()=>{

&#x20;fetch('/api/users')

&#x20; .then(res=>res.json())

&#x20; .then(data=>setUsers(data))

},\[])

```



\---



\# 8. Real Project Questions (5+ years)



Interviewers may ask:



\* How do you \*\*optimize React performance\*\*?

\* How do you \*\*structure large React projects\*\*?

\* How do you \*\*handle authentication\*\*?

\* How do you \*\*handle API caching\*\*?

\* How do you \*\*avoid prop drilling\*\*?

\* How do you \*\*manage global state\*\*?

\* Explain \*\*one complex React feature you built\*\*.



\---



\# 9. Scenario Based Question



\*\*Q:\*\* If React component is re-rendering too much, what will you do?



Answer:



\* Use `React.memo`

\* Use `useMemo`

\* Use `useCallback`

\* Avoid unnecessary state

\* Check parent re-rendering

\* Use lazy loading



Since you are targeting \*\*15+ years roles (Senior Tech Lead / Architect)\*\* and preparing for companies like \*\*Wipro\*\* and \*\*Infosys\*\*, interviewers will focus less on basic React and more on \*\*architecture, performance, scalability, and problem-solving\*\*.



Below is a \*\*structured preparation guide\*\*.



\---



\# 1️⃣ 50 Advanced React Interview Questions



\## React Architecture



1\. How do you design a scalable React application?

2\. What folder structure do you use in enterprise React apps?

3\. How do you separate business logic from UI?

4\. How do you handle reusable components across multiple projects?

5\. How do you design micro-frontend architecture with React?



\---



\## React Internals



6\. Explain React reconciliation algorithm.

7\. What is Fiber architecture in React?

8\. How does React batching work?

9\. What is concurrent rendering?

10\. How does React handle event delegation?



\---



\## Hooks Deep Knowledge



11\. How does `useEffect` cleanup work?

12\. What problems does `useRef` solve?

13\. When should you avoid `useMemo`?

14\. What happens if dependency array is incorrect?

15\. How do you create a custom hook with caching?



\---



\## Performance Optimization



16\. How do you measure React performance?

17\. How do you reduce unnecessary re-renders?

18\. Difference between `React.memo`, `useMemo`, and `useCallback`.

19\. How do you implement virtual scrolling?

20\. How do you optimize large lists (10k items)?



\---



\## State Management



21\. When should you use Redux vs Context API?

22\. How does Redux middleware work?

23\. What is Redux Toolkit?

24\. How do you manage global state in large applications?

25\. How do you prevent unnecessary Redux re-renders?



\---



\## Asynchronous Data Handling



26\. How do you manage API caching?

27\. What is React Query?

28\. What is SWR?

29\. How do you implement retry logic in API calls?

30\. How do you handle race conditions in React?



\---



\## Security



31\. How do you prevent XSS in React?

32\. How do you secure authentication tokens?

33\. How do you implement role-based access control?



\---



\## Testing



34\. How do you test React components?

35\. Difference between Jest and React Testing Library.

36\. How do you mock APIs in tests?

37\. What is snapshot testing?



\---



\## SSR / Next.js



38\. What is server-side rendering?

39\. Difference between SSR, SSG, ISR.

40\. What is hydration in React?

41\. When should you avoid SSR?



\---



\## Large Scale Application



42\. How do you manage feature flags?

43\. How do you implement internationalization?

44\. How do you implement error boundaries?

45\. How do you implement logging in React apps?



\---



\## DevOps \& Deployment



46\. How do you optimize bundle size?

47\. How do you implement CI/CD for React?

48\. How do you manage environment variables?

49\. How do you deploy React applications at scale?

50\. How do you monitor frontend performance?



\---



\# 2️⃣ React Coding Test Questions (Senior Developers)



These are \*\*very common in product companies\*\*.



\---



\## 1. Build a Custom Hook



Create `useDebounce`.



Example:



```javascript

function useDebounce(value, delay){

&#x20;const \[debouncedValue,setDebouncedValue] = useState(value);



&#x20;useEffect(()=>{

&#x20; const handler = setTimeout(()=>{

&#x20;  setDebouncedValue(value)

&#x20; },delay)



&#x20; return ()=>clearTimeout(handler)



&#x20;},\[value])



&#x20;return debouncedValue

}

```



\---



\## 2. Implement Infinite Scroll



Requirements:



\* Load data when user scrolls bottom

\* API pagination

\* Loader state



Key concepts:



\* Intersection Observer

\* useEffect

\* API calls



\---



\## 3. Build a Search Autocomplete



Features:



\* Debounce search

\* API fetch

\* Keyboard navigation

\* Highlight matched text



\---



\## 4. Build a Data Table



Features:



\* Sorting

\* Filtering

\* Pagination

\* Column resizing



\---



\## 5. Implement Drag \& Drop



Example:



\* Reorder list items



Libraries often used:



\* `react-dnd`

\* `react-beautiful-dnd`



\---



\## 6. Build a File Upload Component



Features:



\* Drag \& drop

\* Progress bar

\* File validation

\* Preview image



(Similar to the \*\*invoice upload feature you are building\*\*.)



\---



\## 7. Optimize a Slow Component



Interviewers give code like:



```javascript

const List = ({items})=>{

&#x20;return items.map(item=>{

&#x20; return <Item key={item.id} data={item}/>

&#x20;})

}

```



They expect solution:



\* `React.memo`

\* virtualization

\* memoized props



\---



\# 3️⃣ System Design for React Applications



For \*\*15+ years roles\*\*, you may get a question like:



> Design a large scale React application for an e-commerce platform.



\---



\# Example Architecture



```

Frontend (React / Next.js)



&#x20;       |

API Gateway

&#x20;       |

Microservices

&#x20;       |

Database

```



\---



\# Recommended Folder Structure



```

src

&#x20;├── components

&#x20;├── pages

&#x20;├── hooks

&#x20;├── services

&#x20;├── store

&#x20;├── utils

&#x20;├── constants

&#x20;├── layouts

&#x20;└── styles

```



\---



\# Design Best Practices



\### 1. Component Layering



```

UI Components

Business Components

Pages

```



\---



\### 2. State Management Strategy



Small app → Context API

Medium app → Zustand

Large app → Redux Toolkit



\---



\### 3. API Layer



Create centralized API service:



```

services/

&#x20; api.js

&#x20; authService.js

&#x20; productService.js

```



\---



\### 4. Performance Strategy



\* Lazy loading

\* Code splitting

\* CDN assets

\* image optimization

\* caching



\---



\### 5. Error Handling



Use \*\*Error Boundaries\*\*



```javascript

class ErrorBoundary extends React.Component {

&#x20;componentDidCatch(error,info){

&#x20; logError(error)

&#x20;}

}

```



\---



\### 6. Security



\* JWT authentication

\* Role based access

\* HTTPS

\* CSP headers



\---



\# 4️⃣ Real System Design Question (Asked in Interviews)



Example:



\*\*Design an online document upload system\*\*



Features:



\* Upload files

\* Validate documents

\* Show status

\* Dashboard



Architecture:



```

React UI

&#x20;  |

Upload API

&#x20;  |

File Storage (S3)

&#x20;  |

Processing Service

```



\---



\# 5️⃣ Senior Level Question You May Get



Explain:



\* \*\*How would you design a React app used by 10 million users?\*\*



Expected points:



\* CDN

\* lazy loading

\* caching

\* micro frontends

\* monitoring

\* error tracking



Tools:



\* Sentry

\* Datadog

\* Lighthouse





For \*\*FAANG / top product companies\*\* (like \*\*Google\*\*, \*\*Meta\*\*, \*\*Amazon\*\*, \*\*Netflix\*\*, \*\*Microsoft\*\*), React interviews go \*\*much deeper into internals, architecture, and performance\*\*.



Below are \*\*20 difficult React interview questions\*\* often asked for \*\*Senior / Staff / Architect level\*\*.



\---



\# 1️⃣ React Internals



\### 1. Explain React Fiber architecture.



Expected answer:



React Fiber is the \*\*new reconciliation engine\*\* introduced in React 16.



Purpose:



\* Incremental rendering

\* Better scheduling

\* Pause / resume rendering

\* Prioritize UI updates



Key concepts:



\* Fiber node

\* work loop

\* priority scheduling



\---



\### 2. What happens when you call `setState`?



Steps:



1\. `setState` triggers update

2\. React schedules update

3\. Virtual DOM diffing

4\. Reconciliation

5\. Commit phase updates real DOM



\---



\### 3. What are render phase and commit phase?



Render phase:



\* React calculates changes

\* Can be interrupted



Commit phase:



\* DOM updates happen

\* Cannot be interrupted



\---



\### 4. What is React Concurrent Mode?



Allows React to:



\* pause rendering

\* prioritize updates

\* improve responsiveness



Example:



```javascript

startTransition(()=>{

&#x20;setSearchQuery(value)

})

```



\---



\# 2️⃣ Performance Deep Dive



\### 5. How would you optimize a React app with 50,000 rows?



Possible solutions:



\* virtualization (`react-window`)

\* memoization

\* pagination

\* lazy loading



\---



\### 6. What causes unnecessary re-renders?



Common causes:



\* parent re-render

\* inline functions

\* object reference changes

\* context updates



Solutions:



\* `React.memo`

\* `useCallback`

\* `useMemo`



\---



\### 7. Difference between shallow comparison and deep comparison?



Shallow:



\* compares references



Deep:



\* compares values recursively



React uses \*\*shallow comparison\*\*.



\---



\# 3️⃣ Hooks Edge Cases



\### 8. Why should hooks not be called conditionally?



Hooks rely on \*\*consistent call order\*\* between renders.



If order changes → React cannot match hook states.



\---



\### 9. How does `useRef` avoid re-render?



`useRef` stores mutable values that \*\*persist across renders\*\* without triggering re-render.



Example:



```javascript

const ref = useRef(null)

```



\---



\### 10. Explain stale closure problem.



Example:



```javascript

useEffect(()=>{

&#x20;setInterval(()=>{

&#x20;  console.log(count)

&#x20;},1000)

},\[])

```



The closure captures \*\*old state value\*\*.



Solution:



\* useRef

\* add dependency

\* functional updates



\---



\# 4️⃣ Advanced State Management



\### 11. How would you design global state for a large React app?



Possible architecture:



\* Redux Toolkit

\* Context API

\* Zustand

\* React Query



Best practice:



Separate:



\* UI state

\* server state

\* cache state



\---



\### 12. Difference between client state and server state.



Client state:



\* UI data

\* forms

\* theme



Server state:



\* API data

\* cached responses



Libraries:



\* React Query

\* SWR



\---



\# 5️⃣ React Architecture



\### 13. How would you structure a React project used by 100+ developers?



Expected answer:



\* modular architecture

\* shared component library

\* micro frontends

\* strict linting

\* design system



\---



\### 14. What are micro-frontends?



Multiple independent frontend apps combined into one UI.



Example architecture:



```text

Shell App

&#x20;├── Payments App

&#x20;├── Orders App

&#x20;└── Profile App

```



Tools:



\* Module Federation

\* single-spa



\---



\### 15. What is Module Federation?



Feature of \*\*Webpack\*\* allowing apps to \*\*share components dynamically\*\*.



Used for micro-frontends.



\---



\# 6️⃣ React Rendering Strategies



\### 16. CSR vs SSR vs SSG



| Type | Meaning                |

| ---- | ---------------------- |

| CSR  | Client Side Rendering  |

| SSR  | Server Side Rendering  |

| SSG  | Static Site Generation |



Framework often used:



\*\*Next.js\*\*



\---



\### 17. What is hydration mismatch?



Occurs when:



Server HTML ≠ Client render output.



Common reasons:



\* random values

\* date/time

\* window usage



\---



\# 7️⃣ Security Questions



\### 18. How does React prevent XSS?



React escapes content by default.



Example:



```javascript

<div>{userInput}</div>

```



Dangerous API:



```javascript

dangerouslySetInnerHTML

```



\---



\# 8️⃣ Debugging Questions



\### 19. How do you debug performance issues in React?



Tools:



\* React DevTools profiler

\* Chrome Performance tab

\* Lighthouse



\---



\### 20. How would you reduce bundle size from 5MB to 500KB?



Possible solutions:



\* code splitting

\* dynamic imports

\* tree shaking

\* removing unused libraries

\* CDN assets



Tools:



\* Webpack bundle analyzer



\---



\# Example FAANG System Design Question



> Design \*\*YouTube comment section UI\*\*.



Expected points:



\* pagination

\* lazy loading

\* virtualization

\* caching

\* optimistic updates



\---



\# One Trick FAANG Question



\*\*Question\*\*



Why does this re-render?



```javascript

const data = {name:"John"}



<MyComponent user={data}/>

```



Answer:



Object reference changes every render.



Solution:



```javascript

const data = useMemo(()=>({name:"John"}),\[])

```



\---



✅ Since you are already working with \*\*React + Next.js + AI invoice validation\*\*, a \*\*very likely product-company question\*\* is:



> Design a React UI that uploads documents and validates them with AI.



They expect architecture like:



```

React UI

&#x20;  |

Upload Service

&#x20;  |

AI Validation API

&#x20;  |

Fraud Detection Model

```



