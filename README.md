<h1>NLP Food Chatbot</h1>

<p>A FastAPI-based chatbot designed to handle food orders and provide tracking capabilities. This chatbot can interact with users to take orders, modify existing orders, and track the status of their orders through a conversational interface.</p>

<h2>Features</h2>
<ul>
    <li><strong>Add to Order</strong>: Users can add food items and their quantities to an ongoing order.</li>
    <li><strong>Remove from Order</strong>: Users can remove specified items from their current order.</li>
    <li><strong>Complete Order</strong>: Finalizes the order and provides an order ID along with the total cost.</li>
    <li><strong>Track Order</strong>: Users can check the status of their orders using the order ID.</li>
</ul>

<h2>Technologies Used</h2>
<ul>
    <li><a href="https://fastapi.tiangolo.com/">FastAPI</a>: A modern, fast (high-performance), web framework for building APIs with Python 3.7+.</li>
    <li>SQL Database: The project uses a database to store order information (details to be provided in the <code>db_helper</code>).</li>
</ul>

<h2>Getting Started</h2>

<h3>Prerequisites</h3>
<ul>
    <li>Python 3.7 or later</li>
    <li>A SQL database set up with the necessary tables (details to be provided in the <code>db_helper.py</code>).</li>
</ul>

<h3>Installation</h3>
<ol>
    <li>Clone the repository:
        <pre><code>git clone https://github.com/S-AILAB/FoodChatbot.git
cd FoodChatbot
        </code></pre>
    </li>
    <li>Install the required packages:
        <pre><code>pip install fastapi[all]
        </code></pre>
    </li>
</ol>

<h3>Running the Application</h3>
<ol>
    <li>Start the FastAPI application:
        <pre><code>uvicorn main:app --reload
        </code></pre>
    </li>
    <li>Open your browser and navigate to <code>http://127.0.0.1:8000/docs</code> to view the interactive API documentation provided by FastAPI.</li>
</ol>

<h2>API Endpoints</h2>

<h3><code>POST /</code></h3>
<ul>
    <li><strong>Description</strong>: Handles requests from the chatbot and processes orders based on the user's intent.</li>
    <li><strong>Request Body</strong>: The expected JSON payload structure includes:
        <ul>
            <li><code>queryResult</code>:
                <ul>
                    <li><code>intent</code>: The intent of the user's message.</li>
                    <li><code>parameters</code>: The parameters related to the intent.</li>
                    <li><code>outputContexts</code>: Context information related to the conversation.</li>
                </ul>
            </li>
        </ul>
    </li>
</ul>

<h3>Example Request Payload</h3>
<pre><code>{
  "queryResult": {
    "intent": {
      "displayName": "order.add - context: ongoing-order"
    },
    "parameters": {
      "food-list": ["pizza", "soda"],
      "number": [2, 1]
    },
    "outputContexts": [
      {
        "name": "projects/project-id/agent/sessions/session-id/contexts/ongoing-order",
        "lifespanCount": 5
      }
    ]
  }
}
</code></pre>

<h2>Database Helper</h2>

<p>The project requires a <code>db_helper.py</code> module to handle database interactions. Ensure that the SQL schema is set up to support order management. Refer to the <code>pandeji</code> file for details about the SQL structure.</p>

<h2>Contributing</h2>
<p>Feel free to submit issues or pull requests for any enhancements or fixes.</p>

