# Gemini Flight Manager

## Overview

Gemini Flight Manager is a comprehensive backend system built using FastAPI, designed for managing and simulating flight-related operations. This system provides a robust platform for handling various aspects of flight management, including flight generation, search, and booking functionalities.

The project leverages FastAPI's efficient and easy-to-use framework to create a high-performance, scalable solution ideal for flight data management. It comes equipped with an SQLite database (`flights.db`) pre-populated with initial data, allowing for quick deployment and testing.

Key features of Gemini Flight Manager include:
- Advanced search capabilities to query flights based on criteria like origin, destination, and dates.
- Booking system that handles seat availability across different classes and calculates costs accordingly.

Designed with extensibility and scalability in mind, Gemini Flight Manager is well-suited for both educational purposes and as a foundation for more complex flight management applications.

**For the purposes of Gemini Function Calling, you will only need `search_flights` and `book_flight` functions.

## Requirements
Before you begin, ensure you have the following installed on your system:
- Python 3.6 or higher [Python](https://www.python.org/downloads/)
- FastAPI
- Uvicorn, an ASGI server for FastAPI
  
## Table of content

- Task✨ Setting up Google Gemini
- Task Clone Premade FastAPI Server
- Task☁️ Google Cloud Developer Initialization
- Task📞 Function Calling with Tools
- Task📊 Streamlit Integration
- Task✈️ Build the Book_Flight Tool

## Task✨ Setting up Google Gemini
- Go to the [Google Cloud Platform](https://cloud.google.com/free/?utm_source=google&utm_medium=cpc&utm_campaign=japac-IN-all-en-dr-BKWS-all-core-trial-EXA-dr-1605216&utm_content=text-ad-none-none-DEV_c-CRE_644159077391-ADGP_Hybrid+%7C+BKWS+-+EXA+%7C+Txt+~+GCP_General_core+brand_main-KWID_43700074766895886-aud-970366092687:kwd-6458750523&userloc_9062223-network_g&utm_term=KW_google%20cloud&gad_source=1&gclid=CjwKCAjw48-vBhBbEiwAzqrZVFHOq76jh9J0dgd2lwSHL3oF20yQX_sP4TvFoe6Nw7ofMguovMUk3BoChZ4QAvD_BwE&gclsrc=aw.ds) and Select "Get Started for free".
- Sign in using your Google Account and then provide the necessary details and complete the billing requirments.
- Accept the terms and conditions.
- Complete the payment process to initialize your Google Cloud Account.
- Create a new project (for instance "RadicalX - Gemini Explorer").
- Access the Google Cloud Console.
- Navigation -> Artificial Intelligence -> Vertex AI -> Enable All Recommended APIs

![Setting up Google Gemini](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/2e0e807e-3e51-454e-9d68-f0b3e5799d6b)

## Task Clone Premade FastAPI Server

1. **Clone the Repository**
   
   Start by cloning the repository to your local machine. Use the following command:
   ```bash
   git clone https://github.com/your-username/your-repository.git
   cd your-repository

### Set Up a Virtual Environment (Optional but recommended)

It's a good practice to create a virtual environment for your Python projects. This keeps your project dependencies isolated. If you have `virtualenv` installed, create a new environment with:

```bash
virtualenv venv
source venv/bin/activate
```

### Install Dependencies
Inside the virtual environment, install all necessary dependencies by running:
```bash
pip install -r requirements.txt
```

### Starting the FastAPI Server

After the installation, you can start the FastAPI server using Uvicorn. Navigate to the project directory and run:

```bash
uvicorn main:app
```

### Accessing the API
- With the server running, you can access the API at `http://127.0.0.1:8000.`
- For interactive API documentation, visit `http://127.0.0.1:8000/docs`, where you can test the API endpoints directly from your browser.

**Testing the Endpoints** -> Searching flights for -> origin: BOS, Destination: SFO, Date: 2024-03-17.

![Clone Premade FastAPI Server](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/808fd8cb-f3e9-462a-82f3-575c17f4f6fc)

## Task☁️ Google Cloud Developer Initialization

- Install the Google SDK using this [Link](https://cloud.google.com/sdk/docs/install).
- Run the following command to initialize the SDK:
  ```
  gcloud init
- Sign in using your Google Account credentials.
- Select an existing project or Create a new project
- Set default compute region and zone (Optional Step)
  
![Google Cloud Developer Initialization](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/dec08ec9-c3f1-42c4-9452-b8c4cec797f0)

## Task📞 Function Calling with Tools

- Using FunctionDeclaration to craft the get_search_flights function
```bash
  #Syntax for function declaration
  get_search_flights = generative_models.FunctionDeclaration(
  name="get_search_flights",
  description="Function Description",
  parameters={
      "type": "object",
      "properties": {
          // Define the properties of the parameters here
       }
     }
    )
```
- Encapsulating the get_search_flights in a Tool class, and configuring the GenerativeModel.
```bash
  # Model Syntax
model = GenerativeModel(
"gemini-pro",
tools=[search_tool],
generation_config=config
  )
```

![Function Calling with Tools](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/5ae87b21-e78f-49ee-b0f6-ddf03f443c25)

## Task📊 Streamlit Integration
- Implemented a response handling system and integrated it with Streamlit for effective communication with Google Gemini.

![Streamlit Integration](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/78fb1a34-6a26-4e00-b608-410bfc2f7681)

## Task✈️ Build the Book_Flight Tool

![flightbooking_criteria](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/a37772d8-b408-432d-a7ff-86156f972045)

- Implemented the book_flight function in Flight_Manager.py which sends a POST request to the prebuilt endpoint.
![book_flight function](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/c1c3f604-b891-4010-ac15-501246102e17)

- Created a new FunctionDeclaration for the book_flight_tool, encapsulated it with the search_tool and configured the model
![book_flight tool](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/4f94559a-c15f-43bb-99c2-c968b9ad93e1)

### Working of the Model 

![front-end](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/aa7a0d64-37f0-4104-ac17-78bae33d703a)
![back-end](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/c8f7dcad-4ced-4ae6-aa17-db1ed68edf96)

## Preparing Submission

 - A GitHub repository for the project containing all the project files.
 - Loom Video representing the overall approach.

##  Issues Faced
 - ⚠️ **InvalidArgument: 400 Request contains an invalid argument**

## Acknowledgements
Special thanks to Talha Sabri and Mikhail Ocampo for extending to me the opportunity to embark on and complete this AI Mission.
![RadicalX](https://github.com/mayankpujara/Gemini-Flights/assets/76840933/35585222-6860-43af-9a01-71848b19fde3)



