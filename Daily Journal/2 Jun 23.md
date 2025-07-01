
`app.use(compression()) ` 
Gzips the body to transfer. more load on cpu, however the bottleneck usually stems from network traffic. compressing the size of our data will allow faster response.  