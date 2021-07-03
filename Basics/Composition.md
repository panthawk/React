### What is Composition?

Composition -> To combine simple functions to build more complicated ones.

This principle is behind awsomeness of Reactworking, in React components are a building block, components make React what React is, components follow compositional idea.

composition is nothing but combining two or more functions together, why we need to do this?.

A pure function follow a `DOT` rule `Do One Thing` at a time, so if we want to implenet something complex then we do this by breaking it into simple task that is implemented by the function, and combine all functions together and we get the same result.

another advantages of compositional model is, code reusability, as each components follow `DOT` rule there is no issue of code breaking, put it in a example.

```
function getProfileLink (username) {
 return 'https://github.com/' + username
}

```

this function get a user profile link it is doing a single task of getting a user link.

```
function getProfilePic (username) {
 return 'https://github.com/' + username + '.png?size=200'
}

```

this function get a profile again a single task, these are definetely simple functions now lets combine them.

```
function getProfileData (username) {
 return {
 pic: getProfilePic(username),
 link: getProfileLink(username)
 }
}

```

in the above function we combined the two functions, **A point to remeber here is composition follow a `HAS-A` relationship**

there is doubt, we can get user data by this way also we don't need to worry about composition at all.

```
function getProfileData (username) {
 return {
 pic: 'https://github.com/' + username + '.png?size=200',
 link: 'https://github.com/' + username
 }
}

```

this is technically correct but, but what if the user changed the link to something or we need user link somewere else then we have to repeat the code, so composition help in reusability of code.

> React makes use of the power of composition, heavily! React builds up pieces of a UI using components.

```
<Page />
<Article />
<Sidebar />
```

above are three components, now we combine them together. This

```
<page>
  <Article />
  <Sidebar />
< /Page>

```

Now the Page component has the Article and Sidebar components inside. it's just like what we saw earlier.

In a nutshell components are nothing but a function but there is one difference, unlike traditional functions react components return a `UI` as output instead of somevalue.
