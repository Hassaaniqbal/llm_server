# Microsystem for Analyzing Service Provider Expertise in an On-Demand Household Service Web Application
A microsystem for evaluating the expertise of service providers in an on-demand household service web application. The system utilizes the Llama2 LLM from Meta AI and leverages the LangChain framework for seamless communication with the model.

The primary objective is to provide a comprehensive solution for assessing the knowledge and proficiency of service providers before allowing them to offer their services on the web application. Service providers are required to attend a quiz, and their answers are analyzed by the microsystem using the Llama2 LLM.

The LangChain framework enables efficient interaction with the LLM, allowing the system to process the natural language responses from the service providers and generate insightful evaluations of their expertise.

The microsystem streamlines the onboarding process by automating the initial assessment of service provider expertise, potentially saving time and effort for the administrators. It serves as a reliable screening mechanism to ensure that only qualified service providers are admitted to the web application, enhancing the overall quality of services offered to customers.


## Prerequisites
- Install the latest [Python](https://www.python.org/downloads/) language.
- Run the PhpMyAdmin and MySQL server

## Setup Instructions

1. Install Docker via the official Docker [Website](https://www.docker.com/products/docker-desktop/).
2. After installing Docker, run the command below to pull and run the official [Ollama](https://ollama.com/) container.
    ```sh
    docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
    ```
3. Afterwards run the command below to up and run [Llama 2](https://llama.meta.com/llama2/) model
    ```sh
    docker exec -it ollama ollama run llama2
    ```
4. Clone the repository via the command below
    ```sh
    git clone git@github.com:Hassaaniqbal/llm_server.git
    ```
5. Navigate to the cloned repository and create a `.env` file.
    ```sh
    cd llm_server && touch .env
    ```
6. Copy the contents of `.env.example` file into the `.env` file based on your local environment.

    ```.env
    HOST_NAME=<your-url/>
    PORT_NUMBER=<your-port-number>
    DATABASE_USERNAME=<database-username>
    DATABASE_PASSWORD=<database-password>
    DATABASE_HOSTNAME=<database-hostname>
    DATABASE_NAME=<database-name>
    DATABASE_URI=mysql+mysqldb://${DATABASE_USERNAME}:${DATABASE_PASSWORD}@${DATABASE_HOSTNAME}/${DATABASE_NAME}
    ```
7. Create a Python virtual environment via the command below.
    ```sh
    python -m venv venv
    ```
8. Activate the virtual environment.
    ```ps
    # On Windows Environments
    .\venv\Scripts\activate
    ```

    ```sh
    # On Linux/Mac Environments (Bash)
    source venv/bin/activate
    ```
9. Install the dependencies via the command below
    ```sh
    pip install -r requirements.txt
    ```    
10. Run the LLM server via the command below
    ```sh
    python server.py
    ```
