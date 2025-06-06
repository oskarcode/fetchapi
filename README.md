# Fetch API Demo

## Overview
A practical demonstration of the Fetch API for making HTTP requests in JavaScript. This project showcases modern asynchronous programming techniques and API integration without external libraries.

## Features
- **Fetch API Implementation**: Modern HTTP requests using native browser APIs
- **Asynchronous Programming**: Promises and async/await patterns
- **Error Handling**: Robust error management for network requests
- **JSON Data Processing**: Parsing and handling API responses
- **DOM Manipulation**: Dynamically updating webpage content

## Technologies Used
- **JavaScript (ES6+)** - Modern JavaScript features
- **Fetch API** - Native browser HTTP client
- **Promises/Async-Await** - Asynchronous programming
- **JSON** - Data interchange format
- **HTML5** - Structure and presentation

## Learning Path
In the previous exercise, you created the query URL, called the fetch() function and passed it the query URL and a settings object. Then, you chained a .then() method and passed it two functions as arguments — one to handle the promise if it resolves, and one to handle network errors if the promise is rejected.

In this exercise, you'll now take the information that was returned with the promise and manipulate the webpage!

## Project Structure
```
fetchapi/
├── index.html          # Main HTML file
├── script.js           # Fetch API implementation
├── style.css           # Styling
└── README.md           # This file
```

## Getting Started

### Prerequisites
- Modern web browser with Fetch API support
- Internet connection for API requests
- Basic understanding of JavaScript and HTTP

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/oskarcode/fetchapi.git
   cd fetchapi
   ```

2. Open the project:
   ```bash
   # Simply open index.html in your browser
   open index.html
   ```

## Usage Examples

### Basic Fetch Implementation
```javascript
// Create query URL
const queryURL = 'https://api.example.com/data';

// Fetch with promise handling
fetch(queryURL, {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json'
  }
})
.then(response => {
  if (response.ok) {
    return response.json();
  }
  throw new Error('Network response was not ok');
}, networkError => {
  console.log(networkError.message);
})
.then(jsonResponse => {
  // Manipulate the webpage with the response data
  displayData(jsonResponse);
});
```

### DOM Manipulation with Fetch Data
```javascript
function displayData(data) {
  const container = document.getElementById('data-container');
  container.innerHTML = '';
  
  data.forEach(item => {
    const element = document.createElement('div');
    element.textContent = item.name;
    container.appendChild(element);
  });
}
```

## Key Concepts Covered
1. **Promise Chaining**: Connecting multiple asynchronous operations
2. **Error Handling**: Managing both network and application errors
3. **Response Processing**: Converting responses to usable data
4. **DOM Manipulation**: Updating webpage content dynamically
5. **Asynchronous Flow**: Understanding promise resolution and rejection

## Error Handling Pattern
```javascript
fetch(url)
  .then(response => {
    // Handle successful network request
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    return response.json();
  }, networkError => {
    // Handle network errors (connection issues, etc.)
    console.log('Network Error:', networkError.message);
  })
  .then(data => {
    // Handle successful data processing
    manipulateWebpage(data);
  })
  .catch(error => {
    // Handle any other errors
    console.log('General Error:', error);
  });
```

## Browser Compatibility
Fetch API is supported in:
- **Chrome 42+**
- **Firefox 39+**
- **Safari 10.1+**
- **Edge 14+**

## Learning Objectives
- Understanding the Fetch API workflow
- Promise handling and chaining
- Error management in asynchronous operations
- Dynamic content updates
- Modern JavaScript HTTP requests

## Contributing
1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is open source and available under the [MIT License](LICENSE).

## Resources
- [Fetch API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
- [Promises in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)

## Contact
- GitHub: [@oskarcode](https://github.com/oskarcode)
- Project Link: [https://github.com/oskarcode/fetchapi](https://github.com/oskarcode/fetchapi)

---
*Learn Fetch API with promise handling and DOM manipulation*