# **SEI-Project-01: :camel: El Camello** **REACT HACKATHON**

**Timeframe**: 2 days of pair coding with [Prab Singh](http://https://github.com/Lifearoundhere)

[Here you can check the website!](http://camilabuenamar.github.io/project-02)

![Screenshot of the App](https://imgur.com/RpKrF55.jpg)


Notable Technologies/Libraries used:

- HTML5
- CSS 3
- JavaScript (ES6)
- React (React-DOM, React-Router-DOM, React-Toastify)
- Webpack (with CLI)
- git
- Babel
- Lodashs
- Axios
- Bulma

## Brief:
- Uses 2 public APIs (Reed and Eventbrite).
- App includes Components and router.
- Used Axios requests to get the data.
- Uses Lodash to apply some filters.

## Technologies used:
- HTML5
- CSS 3
- JavaScript (ES6)
- React (React-DOM, React-Router-DOM, React-Toastify)
- Webpack (with CLI)
- git
- Babel
- Lodashs
- Axios
- Bulma

## Approach Taken:
- **Planning:** Before starting the coding we agreed that we wanted to create an API that could be useful for the user's needs. After discussing different options, such as weather forecast, music, restaurants or food we decided to create a job and events App.
- **Choose the APIs:** To choose the API we needed we had some constraints:
  - Not clear documentation of usage.
  - Issues relating to prerequisite applications to get API key,
  - Inconsistent data and API’s that had limited data sets,
For this reason we had to explore different options, read documentation and test different APIs that could satisfy our needs and time limit (2 days).
- **Importing the data:** To import the data we needed to learn the proper way to import exclusively the data that the user requested and merge the both types of responses.
  - Making the requests that make sense: This was one of the most important processes of our app, thats why we had to find a way by which we could make it easy for the user but could work with both APIs. For example the requests for Reed needed to be done by adding info like keywords, location and distance to the url and the key on the header. In the other hand, to make requests to Eventbrite we also needed to add some specific categories we searched before and the key in the URL. In the following code you can see in detail how we made each request.
```javascript
    axios.get('https://cors-anywhere.herokuapp.com/https://www.reed.co.uk/api/1.0/search', {
    params: {
      keywords: this.props.match.params.keyword,
      location: this.props.match.params.location,
      distancefromlocation: 10
    },
    headers: {
      Authorization: `Basic ${reedKey}`,
      'X-Requested-With': 'XMLHttpRequest'
    }

    axios.get('https://cors-anywhere.herokuapp.com/https://www.eventbriteapi.com/v3/events/search?', {
      params: {
        token: eventbriteKey,
        'location.address': this.props.match.params.location,
        'location.within': '10km',
        expand: 'venue',
        categories: '101,102'

      },
      headers: { Authorization: `Bearer ${eventbriteKey}` }
    })
```    

  - Merging the data: This part of the process was also very challenging because as the information of each API was different, we needed to display it different. This meant we had to do it by extracting the relevant indexes and blend them. Also we decided to create a new tag 'isA' or 'isB' to different if it was a job offer or an event.

- **Visuals:** We wanted to make it visually easy to understand the difference between both types of data and which data was more relevant for each type of information. Thats why I created two different cards with Bulma. In the event card a cover image and date were very relevant, meanwhile for the job offer card the information was more related to role, description and company. Having this in mind we did cards that could look harmonious but at the same time differentiate. The fact that the images of the events were so colorful was very distracting by the side of the job offers, for this reason I applied a black and white filter, for the purpose of our webpage the events and jobs should be at the same level. For the colors I did something simple, black and white with a deep pink to contrast the information.

- **The Name:** El Camello means "The Camel" in spanish. We wanted to make a game of words that sounded fun but at the same time made sense. For this reason I propose "El Camello" a word that means Job, Tasks or Workload in different countries of Latin America, like mine, Colombia.

## Wins and blockers:
The biggest win was learning how different APIs work, discover diverse documentation and learn how they worked, how to made special requests, use keys and extract information from the responses. Given the small amount of time we had, we got a lot done, and the final application is basic, but functional. Merging the two datasets from each API together and understanding a way to made them both in the same level was a challenge. Also was the first time we were pair coding which meant we had to communicate more than usual (which was a little difficult since english is not my first language) and solve discussion points and negotiate our differences.

## Future features:
Sort better the cards so theres a specific order between the jobs and events card to make it visually more attractive and not just randomly shuffle. Also the option to apply filters to each group of cards separately.
