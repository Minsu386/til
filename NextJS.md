



# How Routing and Navigation Works
----

Application code is automatically code split. 
Two ways NextJS pre-fetches
1) If NextJS sees a `Link` tag, it will pre-fetch that code in the background for the user. 
2) `router.prefetch()`: useRouter hook can be used to prefetch routes programmatically
