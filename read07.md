# What Google Learned From Its Quest to Build the Perfect Team

![](https://static01.nyt.com/images/2016/02/28/magazine/28mag-teams1/28mag-teams1-superJumbo.jpg?quality=90&auto=webp)

# psychological safety talk

One of the best steps to working with an ideal team is to be comfortable in dealing with and not to be nervous about saying any idea if you do not get that but your team
The differences between you in all areas of your life do not matter as much as respect and acceptance, and for the team to work as a group, not as individual friends so we should choose our team carefully 

software engineers are encouraged to work together, in part because studies show that groups tend to innovate faster, see mistakes more quickly and find better solutions to problems. Studies also show that people working in teams tend to achieve better results and report higher job satisfaction


 After extensive research in studying the work of the teams like **Project Aristotle** What interested the researchers most, however, was that teams that did well on one assignment usually did well on all the others. 


 ## SuperAgent
 SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!

```js
request
   .post('/api/pet')
   .send({ name: 'Manny', species: 'cat' })
   .set('X-API-Key', 'foobar')
   .set('Accept', 'application/json')
   .then(res => {
      alert('yay got ' + JSON.stringify(res.body));
   });
   ```

   **Request basics**
   A request can be initiated by invoking the appropriate method on the request object, then calling .then() (or .end() or await) to send the request. For example a simple GET request:

   ```js
   request
   .get('/search')
   .then(res => {
      // res.body, res.headers, res.status
   })
   .catch(err => {
      // err.message, err.response
   });

   ```
   HTTP method may also be passed as a string:
   ``` js
   request('GET', '/search').then(success, failure);

```

**Setting header fields**

   Setting header fields is simple, invoke .set() with a field name and value:

   **Get Request**

   The .query() method accepts objects, which when used with the GET method will form a query-string. the path 
