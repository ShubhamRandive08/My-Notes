
### **Performance Testing**  <br>

Performance testing is a type of software testing that evaluates how an application behaves under different workloads. It ensures that the system meets performance expectations in terms of **speed, scalability, stability, and responsiveness**.<br>

---

### **Types of Performance Testing<br>**

1. **Load Testing** <br>
    
    - Measures system performance under expected user load.<br>
    - Example: Checking if a website handles 1,000 users at once.<br>
2. **Stress Testing** <br>
    
    - Evaluates system behavior under extreme conditions (beyond normal usage).<br>
    - Example: Simulating a traffic surge on Black Friday.<br>
3. **Spike Testing** <br>
    
    - Tests how the system handles sudden and extreme increases in load.<br>
    - Example: A flash sale where traffic spikes instantly.<br>
4. **Soak (Endurance) Testing** <br>
    
    - Measures system stability over an extended period.<br>
    - Example: Running a test for 24 hours to check memory leaks.<br>
5. **Scalability Testing** <br>
    
    - Determines how the system scales with increased user load.<br>
    - Example: Checking if performance remains steady when adding more servers.<br>
6. **Volume Testing** <br>
    
    - Evaluates how a system handles large amounts of data.<br>
    - Example: Testing a database with millions of records.<br>

---

### **Why is Performance Testing Important?**<br>

 Ensures a smooth user experience  <br>
 Prevents crashes and downtime  <br>
 Identifies bottlenecks and weaknesses  <br>
 Helps with capacity planning<br>

[k6](https://k6.io/) is an open-source performance testing tool for testing the reliability and scalability of applications. It is designed primarily for load testing APIs, web applications, and microservices.<br>

### Key Features:<br>

- **Scripting with JavaScript**: Tests are written in JavaScript, making it developer-friendly.<br>
- **CLI-Based Execution**: Runs from the command line for easy automation and integration into CI/CD pipelines.<br>
- **Lightweight and Efficient**: Uses a Go-based runtime, making it efficient in resource usage.<br>
- **Built-in Metrics and Reports**: Provides real-time statistics and analytics for performance insights.<br>
- **Cloud and Local Testing**: Supports both local and distributed cloud-based load testing.<br>

#### Installation Of K6 :
- Go on Google
- Search k6 documentation
- Click on *`Click on GET STARTED WITH K6`*
- Go to `SET UP` - Go to `INSTALL K6` Then Click On `the latest official installer`

Metric Type :<br>
Metric     Type <br>

Rate ---> rate <br>

Counter ---> count  <br>

Tread --> min, max, p(90), p(95) <br>

Gorge ---> value <br>

**Tags**<br>
Tags are a powerful way categorize your k6 entities and filter test results<br>
System tag : `method, status, proto, `
Other defined tag  ( Custom Tags ): The tag is created by user for there requirement
<br>
05/03/2025
<br>
Organizing request in Group in K6 :<br>
- Group - 


06 / 03 / 2025 <br>
Threshold for group : <br>

Group duration : <br>
Structur 

