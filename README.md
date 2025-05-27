# MercadoLibre JMeter Search Sampler

## Overview
This project provides a custom JMeter sampler for performing searches on MercadoLibre, one of Latin America's largest e-commerce platforms. The sampler allows you to create load tests and performance tests against MercadoLibre's search functionality.

## Features
- Custom Java sampler for JMeter
- Configurable search terms and base URL
- HTTP response metrics collection
- Simple integration with existing JMeter test plans

## Requirements
- Apache JMeter 5.0 or higher
- Java 11 or higher
- Maven (for building the project)

## Installation

### Building the JAR
1. Clone this repository
2. Build the project using Maven:
   ```
   mvn clean package
   ```
3. The resulting JAR file will be located in the `target` directory

### Adding to JMeter
1. Copy the generated JAR file to JMeter's `lib/ext` directory
2. Restart JMeter to load the new sampler

## Usage

### Adding the Sampler to a Test Plan
1. Start JMeter
2. Create a new Test Plan or open an existing one
3. Add a Thread Group
4. Right-click on the Thread Group and select: Add → Sampler → Java Request
5. Select "org.grupo11.MercadoLibreSearchSampler" from the classname dropdown

### Configurable Parameters

| Parameter  | Description | Default Value |
|------------|-------------|---------------|
| searchTerm | The term to search for on MercadoLibre | "celular samsung" |
| url        | The base URL for MercadoLibre | "https://www.mercadolibre.com.ar" |

### Example Test Plan
1. Create a Thread Group with 10 users
2. Add the MercadoLibre Search Sampler
3. Configure the search term (e.g., "laptop lenovo")
4. Add listeners to view results (e.g., View Results Tree, Summary Report)
5. Run the test plan

## How It Works
The sampler sends HTTP GET requests to the configured MercadoLibre URL. It collects response data, including:
- Response code
- Response time
- Response body (truncated in logs for readability)

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.