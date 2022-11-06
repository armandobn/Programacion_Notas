```jsx
const users = [
  {
    id: 1,
    name: "Rayan ray",
    image: "https://robohash.org/user2",
  },
  {
    id: 1,
    name: "Joe",
    image: "https://robohash.org/user2",
  },
];
```

```jsx
root.render(
  <>
    {users.map((user, index) => {
      return <h1 key={index}>{user.name}</h1>;
    })}
  </>
);
```