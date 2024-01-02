
## How Routing and Navigation Works
----

Application code is automatically code split. 
Two ways NextJS pre-fetches
1) If NextJS sees a `Link` tag, it will pre-fetch that code in the background for the user. 
2) `router.prefetch()`: useRouter hook can be used to prefetch routes programmatically







## Document Higher Order Components
----
A higher-order component is a pure function that wraps `WrappedComponent` and outputs `EnchancedComponents`
```NextJS
const EnhancedComponent = higherOrderComponent(WrappedComponent);
```

[Custom Document](https://nextjs.org/docs/pages/building-your-application/routing/custom-document)

