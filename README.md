- 👋 Hi, I’m @TRIXMI
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
TRIXMI/TRIXMI is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
(\\wsl.localhost)
alien_house_api/
├── app.py          # Main Flask/FastAPI application
├── model/
│   ├── model.py     # AI model definition
│   └── weights.h5   # Trained model weights
├── utils/
│   ├── audio_utils.py # Audio feature extraction
│   └── text_utils.py  # Text feature extraction
├── db/
│   └── db.py         # Database interaction
├── Dockerfile        # Docker configuration
├── requirements.txt  # Python dependencies
└── deploy.sh         # Deployment script
https://developer.android.com/studio/inspect/database?utm_source=android-studio#open
export _JAVA_OPTIONS="-Djava.net.preferIPv6Addresses=true"
Fatal signal 11 (SIGSEGV), code 1 (SEGV_MAPERR)
https://developer.android.com/studio/known-issues#ki-android-11-db-inspector
export _JAVA_OPTIONS="-Djava.net.preferIPv6Addresses=true"
alien_house_api/
├── app.py          # Main Flask/FastAPI application
├── model/
│   ├── model.py     # AI model definition
│   └── weights.h5   # Trained model weights
├── utils/
│   ├── audio_utils.py # Audio feature extraction
│   └── text_utils.py  # Text feature extraction
├── db/
│   └── db.py         # Database interaction
├── Dockerfile        # Docker configuration
├── requirements.txt  # Python dependencies
└── deploy.sh         # Deployment script
(\\wsl.localhost)
FROM python:3.9

WORKDIR /code

# Create a non-root user and group
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Copy and install requirements first to leverage Docker layer caching
COPY ./requirements.txt /code/requirements.txt
RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt

# Copy application code, changing ownership to the non-root user
COPY --chown=appuser:appgroup ./app /code/app

# Switch to the non-root user
USER appuser

# Expose the port the app runs on
EXPOSE 80

# Command to run the application using a production server
# Ensure 'app.main:app' matches your FastAPI app instance location
# (e.g., if your FastAPI instance is `my_api = FastAPI()` in `app/server.py`,
# it would be `app.server:my_api`)
CMD ["gunicorn", "-k", "uvicorn.workers.UvicornWorker", "app.main:app", "--bind", "0.0.0.0:80"]

# If behind a proxy:
# CMD ["gunicorn", "-k", "uvicorn.workers.UvicornWorker", "app.main:app", "--bind", "0.0.0.0:80", "--forwarded-allow-ips='*'"]
# Note: For Gunicorn with Uvicorn worker, proxy headers are often handled by Uvicorn.
# The Uvicorn equivalent of --proxy-headers is --forwarded-allow-ips (e.g., --forwarded-allow-ips='*').
# Or you can pass Uvicorn args directly:
# CMD ["gunicorn", "app.main:app", "-k", 
import os
import sys

if not __package__:
# Make CLI runnable from source tree with
#    python src/package
package_source_path = os.path.dirname(os.path.dirname(__file__))
sys.path.insert(0, package_source_path).
├── README.md
├── noxfile.py
├── pyproject.toml
├── setup.py
├── awesome_package/
│   ├── __init__.py
│   └── module.py
└── tools/
├── generate_awesomeness.py
└── decrease_world_suck.py.
├── README.md
├── noxfile.py
├── pyproject.toml
├── setup.py
├── src/[](https://drive.usercontent.google.com/download?id=14KyEgwY3fXWjQzH_k-q5H8YXCAY-O4jc&export=download&authuser=0&confirm=t&uuid=a8232d71-8c69-4334-adf8-dd8a17f312d6&at=ALoNOgmEeUwXuoeqVgEsnyv8VQpE:1749476272152)
│    └── awesome_package/
│       ├── __init__.py
│       └── module.py
└── tools/
├── generate_awesomeness.py
└── decrease_world_suck.py.
├── README.md
├── noxfile.pyhttps://drive.usercontent.google.com/download?id=14KyEgwY3fXWjQzH_k-q5H8YXCAY-O4jc&export=download&authuser=0&confirm=t&uuid=a8232d71-8c69-4334-adf8-dd8a17f312d6&at=ALoNOgmEeUwXuoeqVgEsnyv8VQpE:1749476272152
import 'package:flutter/material.dart';
import 'dart:math';

class AlienTechCover {
static Widget generate(String textInput) {
// 1. Keyword Extraction (Simplified)
List<String> keywords = textInput.split(' ');

    // 2. Base Color
    Color baseColor = keywords.contains('blue') ? Colors.blue : Colors.green;

    // 3. Number of Circuit Lines
    int numLines = keywords.length + 5;

    return Container(
      decoration: BoxDecoration(
        color: baseColor.shade900, // Dark background
      ),
      child: Stack(
        children: [
          // Circuit Lines
          for (int i = 0; i < numLines; i++)
            Positioned(
              left: Random().nextDouble() * 300,
              top: Random().nextDouble() * 300,
              child: Container(
                width: Random().nextDouble() * 50 + 10,
                height: 2,
                color: baseColor.shade200.withOpacity(0.5), // Glowing line
              ),
            ),
          // Central Glow
          Center(
            child: Container(
              width: 80,
              height: 80,
              decoration: BoxDecoration(
                color: baseColor.shade400.withOpacity(0.7),
                shape: BoxShape.circle,
                boxShadow: [
                  BoxShadow(
                    color: baseColor.shade400,
                    blurRadius: 20,
                    spreadRadius: 5,
                  ),
                ],
              ),
            ),
          ),
          // Hexagon Pattern
          for (int i = 0; i < 5; i++)
            Positioned(
              left: Random().nextDouble() * 300,
              top: Random().nextDouble() * 300,
              child: Transform.rotate(
                angle: Random().nextDouble() * pi * 2,
                child: CustomPaint(
                  size: Size(20, (20 * 0.8660254037844386)), // Hexagon
                  painter: HexagonPainter(color: baseColor.shade300.withOpacity(0.6)),
                ),
              ),
            ),
        ],
      ),
    );
}
}

class HexagonPainter extends CustomPainter {
final Color color;
HexagonPainter({required this.color});

@override
void paint(Canvas canvas, Size size) {
final path = Path();
final height = size.height;
final width = size.width;

    path.moveTo(size.width / 2, 0);
    path.lineTo(width, height * 0.25);
    path.lineTo(width, height * 0.75);
    path.lineTo(size.width / 2, height);
    path.lineTo(0, height * 0.75);
    path.lineTo(0, height * 0.25);
    path.close();

    final paint = Paint()
      ..color = color
      ..style = PaintingStyle.fill;

    canvas.drawPath(path, paint);
}List<String> keywords = textInput.split(' ');
Color baseColor = keywords.contains('blue') ? Colors.blue : Colors.green;
int numLines = keywords.length + 5;
int numLines = keywords.length + 5;
return Container(
decoration: BoxDecoration(
color: baseColor.shade900, // Dark background
),
child: Stack(
children: [
// ... visual elements ...
],
),
);for (int i = 0; i < numLines; i++)
Positioned(
left: Random().nextDouble() * 300,
top: Random().nextDouble() * 300,
child: Container(
width: Random().nextDouble() * 50 + 10,
height: 2,
color: baseColor.shade200.withOpacity(0.5), // Glowing line
),
@override,for (int i = 0; i < numLines; i++)
Positioned(
left: Random().nextDouble() * 300,
top: Random().nextDouble() * 300,
child: Container(
width: Random().nextDouble() * 50 + 10,
height: 2,
color: baseColor.shade200.withOpacity(0.5), // Glowing line
),
),Center(
child: Container(
width: 80,
height: 80,
decoration: BoxDecoration(
color: baseColor.shade400.withOpacity(0.7),
shape: BoxShape.circle,
boxShadow: [
BoxShadow(
color: baseColor.shade400,
blurRadius: 20,
spreadRadius: 5,
),
],
),
),
),for (int i = 0; i < 5; i++)
Positioned(
left: Random().nextDouble() * 300,
top: Random().nextDouble() * 300,
child: Transform.rotate(
angle: Random().nextDouble() * pi * 2, // Random rotation (0 to 360 degrees)
child: CustomPaint(
size: Size(20, (20 * 0.8660254037844386)), // Hexagon dimensions
painter: HexagonPainter(color: baseColor.shade300.withOpacity(0.6)),
),
),
),// In some build method of a Widget
Scaffold(
appBar: AppBar(title: Text("Alien Tech Demo")),
body: Center( // Or any other layout widget
child: SizedBox(
width: 300, // Define the bounds for the cover
height: 300,
child: AlienTechCover.generate("blue core energy field"),
),
),
)alien house music
)
bool shouldRepaint(covariant CustomPainter oldDelegate) {
return false;
}
}
├── pyproject.toml
├── setup.py
├── src/
│    └── awesome_package/
│       ├── __init__.py
│       └── module.py
└── tools/
├── generate_awesomeness.py
└── decrease_world_suck.py"uvicorn.workers.UvicornWorker", "--bind", "0.0.0.0:80", "--workers", "4", "--forwarded-allow-ips='*'"]# Assuming your FastAPI app instance is named `app` in `app/main.py`
CMD ["gunicorn", "-k", "uvicorn.workers.UvicornWorker", "app.main:app", "--bind", "0.0.0.0:80"]{
"cells": [
{
"cell_type": "markdown",
"metadata": {
"id": "Tce3stUlHN0L"
},
"source": [
"##### Copyright 2024 Google LLC."
]
},
{
"cell_type": "code",
"execution_count": 1,
"metadata": {
"cellView": "form",
"id": "tuOe1ymfHZPu"
},
"outputs": [],
"source": [
"# @title Licensed under the Apache License, Version 2.0 (the \"License\");\n",
"# you may not use this file except in compliance with the License.\n",
"# You may obtain a copy of the License at\n",
"#\n",
"# https://www.apache.org/licenses/LICENSE-2.0\n",
"#\n",
"# Unless required by applicable law or agreed to in writing, software\n",
"# distributed under the License is distributed on an \"AS IS\" BASIS,\n",
"# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.\n",
"# See the License for the specific language governing permissions and\n",
"# limitations under the License."
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "4BkXaeuqGFzD"
},
"source": [
"# Code Execution in the Gemini API\n",
"\n",
"<table align=\"left\">\n",
"  <td>\n",
"    <a target=\"_blank\" href=\"https://colab.research.google.com/github/google-gemini/cookbook/blob/main/quickstarts/Code_Execution.ipynb\"><img src=\"https://github.com/google-gemini/cookbook/blob/ce76bbe63554b4fceeba6bf6c2ef4b264d3d2da9/images/colab_logo_32px.png?raw=1\" />Run in Google Colab</a>\n",
"  </td>\n",
"</table>\n"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "CDhVGsAHhwG5"
},
"source": [
"The Gemini API [code execution](https://ai.google.dev/gemini-api/docs/code-execution) feature enables the model to generate and run Python code based on plain-text instructions that you give it. It can learn iteratively from the results until it arrives at a final output.\n",
"\n",
"This notebook is a walk through of how to use this feature."
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "kQoJWW8lM48-"
},
"source": [
"### Set up"
]
},
{
"cell_type": "code",
"execution_count": 2,
"metadata": {
"id": "6rshwediCXto"
},
"outputs": [
{
"name": "stdout",
"output_type": "stream",
"text": [
"\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m165.0/165.0 kB\u001b[0m \u001b[31m2.4 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
"\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m725.4/725.4 kB\u001b[0m \u001b[31m10.5 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
"\u001b[?25h"
]
}
],
"source": [
"!pip install -Uq \"google-generativeai>=0.7.2\""
]
},
{
"cell_type": "code",
"execution_count": 3,
"metadata": {
"id": "OsxWu_BI50Ex"
},
"outputs": [
{
"data": {
"application/vnd.google.colaboratory.intrinsic+json": {
"type": "string"
},
"text/plain": [
"'0.8.1'"
]
},
"execution_count": 3,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"import google.generativeai as genai\n",
"genai.__version__"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "b276ccf016b9"
},
"source": [
"To run the following cell, your API key must be stored it in a Colab Secret named `GOOGLE_API_KEY`. If you don't already have an API key, or you're not sure how to create a Colab Secret, see the [Authentication](https://github.com/google-gemini/cookbook/blob/main/quickstarts/Authentication.ipynb) quickstart for an example."
]
},
{
"cell_type": "code",
"execution_count": 4,
"metadata": {
"id": "itMjtruv7QqE"
},
"outputs": [],
"source": [
"from google.colab import userdata\n",
"genai.configure(api_key=userdata.get('GOOGLE_API_KEY'))"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "rvmIpRX5IN1q"
},
"source": [
"Tweak CSS for display in Colab"
]
},
{
"cell_type": "code",
"execution_count": 5,
"metadata": {
"id": "kS3JQzazOI48"
},
"outputs": [],
"source": [
"from IPython.display import HTML, Markdown\n",
"\n",
"def set_css_in_cell_output(unused):\n",
"  display(HTML(\"\"\"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>\"\"\"))\n",
"\n",
"get_ipython().events.register('pre_run_cell', set_css_in_cell_output)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "q-jdBwXlM67j"
},
"source": [
"## Pass `\"code_execution\"` as a `tool`\n",
"\n",
"When initiating the model, pass `\"code_execution\"` as a `tool` to tell the model that it is allowed (but not forced) to generate and run code."
]
},
{
"cell_type": "code",
"execution_count": 6,
"metadata": {
"id": "BFxIcGkxbq3_"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"model = genai.GenerativeModel(model_name='gemini-1.5-flash', tools=\"code_execution\")"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "mZgn5tm-NCfH"
},
"source": [
"## Call `generate_content`"
]
},
{
"cell_type": "code",
"execution_count": 7,
"metadata": {
"id": "u2DRvZZde2C6"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"result = model.generate_content(\"What is the sum of the first 50 prime numbers?\"\n",
"                                \"Generate and run code for the calculation, and make sure you get all 50.\")"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "8uJ-Fk1I_AH8"
},
"source": [
"The model returns a list of parts including `text`, `executable_code`, and `execution_result` parts."
]
},
{
"cell_type": "code",
"execution_count": 8,
"metadata": {
"id": "E1_KEd4P-_YB"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/plain": [
"[['text'], ['executable_code'], ['code_execution_result'], ['text']]"
]
},
"execution_count": 8,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"[\n",
"    list(type(p).to_dict(p))\n",
"    for p in result.candidates[0].content.parts\n",
"]"
]
},
{
"cell_type": "code",
"execution_count": 9,
"metadata": {
"id": "JtL3wwKJA0Jf"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"text: \"I will determine the sum of the first 50 prime numbers. \\n\\nFirst, I need to define what a prime number is. A prime number is a whole number greater than 1 that has only two divisors: 1 and itself. \\n\\nTo calculate the sum of the first 50 prime numbers, we can use the following Python code:\\n\\n\"\n",
"\n",
"\n",
"executable_code {\n",
"  language: PYTHON\n",
"  code: \"\\ndef is_prime(num):\\n    \\\"\\\"\\\"\\n    Checks if a number is prime.\\n    \\\"\\\"\\\"\\n    if num <= 1:\\n        return False\\n    for i in range(2, int(num**0.5) + 1):\\n        if num % i == 0:\\n            return False\\n    return True\\n\\n\\ndef find_primes(n):\\n    \\\"\\\"\\\"\\n    Generates a list of the first n prime numbers.\\n    \\\"\\\"\\\"\\n    primes = []\\n    count = 0\\n    num = 2\\n    while count < n:\\n        if is_prime(num):\\n            primes.append(num)\\n            count += 1\\n        num += 1\\n    return primes\\n\\n\\nprimes = find_primes(50)\\nsum_primes = sum(primes)\\n\\nprint(f\\\"The sum of the first 50 prime numbers is: {sum_primes}\\\")\\n\"\n",
"}\n",
"\n",
"\n",
"code_execution_result {\n",
"  outcome: OUTCOME_OK\n",
"  output: \"The sum of the first 50 prime numbers is: 5117\\n\"\n",
"}\n",
"\n",
"\n",
"text: \"The code first defines two functions: `is_prime` and `find_primes`. `is_prime` takes a number as input and returns `True` if the number is prime and `False` otherwise. It checks if the number is less than or equal to 1, in which case it is not prime. It then iterates through all numbers from 2 up to the square root of the input number. For each number, it checks if the input number is divisible by the current number. If it is, then the number is not prime and the function returns `False`. Otherwise, it continues to the next number. If the function reaches the end of the loop without returning `False`, then the number is prime and the function returns `True`.\\n\\n`find_primes` takes an integer `n` as input and returns a list of the first `n` prime numbers. It initializes an empty list `primes` and a counter `count` to 0. It then iterates through all numbers starting from 2. For each number, it calls the `is_prime` function to check if the number is prime. If it is, it appends the number to the `primes` list and increments the counter by 1. The loop continues until the counter reaches `n`. Finally, the function returns the `primes` list.\\n\\nThe code then calls the `find_primes` function with the argument 50 to get a list of the first 50 prime numbers. It then calls the `sum` function on the list to get the sum of all the elements in the list, which is the sum of the first 50 prime numbers. Finally, it prints the sum to the console.\\n\\nThe code successfully calculates the sum of the first 50 prime numbers, which is 5117.\"\n",
"\n",
"\n"
]
}
],
"source": [
"for part in result.candidates[0].content.parts:\n",
"  print(part)\n",
"  print()"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "TOKHOJQ6_LZO"
},
"source": [
"The `.text` property formats the parts into Markdown compatible text:"
]
},
{
"cell_type": "code",
"execution_count": 10,
"metadata": {
"id": "Qe_aoIGoMlMc"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"I will determine the sum of the first 50 prime numbers. \n",
"\n",
"First, I need to define what a prime number is. A prime number is a whole number greater than 1 that has only two divisors: 1 and itself. \n",
"\n",
"To calculate the sum of the first 50 prime numbers, we can use the following Python code:\n",
"\n",
"\n",
"``` python\n",
            "def is_prime(num):\n",
            "    \"\"\"\n",
            "    Checks if a number is prime.\n",
            "    \"\"\"\n",
            "    if num <= 1:\n",
            "        return False\n",
            "    for i in range(2, int(num**0.5) + 1):\n",
            "        if num % i == 0:\n",
            "            return False\n",
            "    return True\n",
            "\n",
            "\n",
            "def find_primes(n):\n",
            "    \"\"\"\n",
            "    Generates a list of the first n prime numbers.\n",
            "    \"\"\"\n",
            "    primes = []\n",
            "    count = 0\n",
            "    num = 2\n",
            "    while count < n:\n",
            "        if is_prime(num):\n",
            "            primes.append(num)\n",
            "            count += 1\n",
            "        num += 1\n",
            "    return primes\n",
            "\n",
            "\n",
            "primes = find_primes(50)\n",
            "sum_primes = sum(primes)\n",
            "\n",
            "print(f\"The sum of the first 50 prime numbers is: {sum_primes}\")\n",
            "\n",
            "```\n",
"```\n",
            "The sum of the first 50 prime numbers is: 5117\n",
            "\n",
            "```\n",
"The code first defines two functions: `is_prime` and `find_primes`. `is_prime` takes a number as input and returns `True` if the number is prime and `False` otherwise. It checks if the number is less than or equal to 1, in which case it is not prime. It then iterates through all numbers from 2 up to the square root of the input number. For each number, it checks if the input number is divisible by the current number. If it is, then the number is not prime and the function returns `False`. Otherwise, it continues to the next number. If the function reaches the end of the loop without returning `False`, then the number is prime and the function returns `True`.\n",
"\n",
"`find_primes` takes an integer `n` as input and returns a list of the first `n` prime numbers. It initializes an empty list `primes` and a counter `count` to 0. It then iterates through all numbers starting from 2. For each number, it calls the `is_prime` function to check if the number is prime. If it is, it appends the number to the `primes` list and increments the counter by 1. The loop continues until the counter reaches `n`. Finally, the function returns the `primes` list.\n",
"\n",
"The code then calls the `find_primes` function with the argument 50 to get a list of the first 50 prime numbers. It then calls the `sum` function on the list to get the sum of all the elements in the list, which is the sum of the first 50 prime numbers. Finally, it prints the sum to the console.\n",
"\n",
"The code successfully calculates the sum of the first 50 prime numbers, which is 5117.\n"
]
}
],
"source": [
"print(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "hxfUg10DOxgE"
},
"source": [
"In a notebook you can display the Markdown:"
]
},
{
"cell_type": "code",
"execution_count": 11,
"metadata": {
"id": "N-c7VXWoEFQB"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "I will determine the sum of the first 50 prime numbers. \n\nFirst, I need to define what a prime number is. A prime number is a whole number greater than 1 that has only two divisors: 1 and itself. \n\nTo calculate the sum of the first 50 prime numbers, we can use the following Python code:\n\n\n``` python\ndef is_prime(num):\n    \"\"\"\n    Checks if a number is prime.\n    \"\"\"\n    if num <= 1:\n        return False\n    for i in range(2, int(num**0.5) + 1):\n        if num % i == 0:\n            return False\n    return True\n\n\ndef find_primes(n):\n    \"\"\"\n    Generates a list of the first n prime numbers.\n    \"\"\"\n    primes = []\n    count = 0\n    num = 2\n    while count < n:\n        if is_prime(num):\n            primes.append(num)\n            count += 1\n        num += 1\n    return primes\n\n\nprimes = find_primes(50)\nsum_primes = sum(primes)\n\nprint(f\"The sum of the first 50 prime numbers is: {sum_primes}\")\n\n```\n```\nThe sum of the first 50 prime numbers is: 5117\n\n```\nThe code first defines two functions: `is_prime` and `find_primes`. `is_prime` takes a number as input and returns `True` if the number is prime and `False` otherwise. It checks if the number is less than or equal to 1, in which case it is not prime. It then iterates through all numbers from 2 up to the square root of the input number. For each number, it checks if the input number is divisible by the current number. If it is, then the number is not prime and the function returns `False`. Otherwise, it continues to the next number. If the function reaches the end of the loop without returning `False`, then the number is prime and the function returns `True`.\n\n`find_primes` takes an integer `n` as input and returns a list of the first `n` prime numbers. It initializes an empty list `primes` and a counter `count` to 0. It then iterates through all numbers starting from 2. For each number, it calls the `is_prime` function to check if the number is prime. If it is, it appends the number to the `primes` list and increments the counter by 1. The loop continues until the counter reaches `n`. Finally, the function returns the `primes` list.\n\nThe code then calls the `find_primes` function with the argument 50 to get a list of the first 50 prime numbers. It then calls the `sum` function on the list to get the sum of all the elements in the list, which is the sum of the first 50 prime numbers. Finally, it prints the sum to the console.\n\nThe code successfully calculates the sum of the first 50 prime numbers, which is 5117.",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 11,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"from IPython.display import Markdown\n",
"Markdown(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "avyoRa0XF5wR"
},
"source": [
"Note: you can also set the `tools` argument on the call to `generate_content`:"
]
},
{
"cell_type": "code",
"execution_count": 12,
"metadata": {
"id": "DL2mRlNTF5JN"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"model2 = genai.GenerativeModel(model_name='gemini-1.5-flash')"
]
},
{
"cell_type": "code",
"execution_count": 13,
"metadata": {
"id": "fY062-nsGLBu"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"response = model2.generate_content(\n",
"    \"Write code to count how many letter r in the word strawberry\",\n",
"    tools=\"code_execution\")"
]
},
{
"cell_type": "code",
"execution_count": 14,
"metadata": {
"id": "fQY1_501GfP-"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "\n``` python\nword = \"strawberry\"\ncount = 0\nfor letter in word:\n  if letter == \"r\":\n    count += 1\nprint(f'There are {count} letter \"r\" in the word \"strawberry\"')\n\n```\n```\nThere are 3 letter \"r\" in the word \"strawberry\"\n\n```\nI iterated over each letter in the word \"strawberry\" and counted how many times the letter \"r\" appears. The code counted 3 \"r\"s in the word \"strawberry\". \n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 14,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"Markdown(response.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "4QTF9Lk6Ds-b"
},
"source": [
"## Chat\n",
"\n",
"It works the same when using a `chat`:"
]
},
{
"cell_type": "code",
"execution_count": 15,
"metadata": {
"id": "_19QkCnQEZSu"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"chat = model.start_chat()"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "9b2d47bf0927"
},
"source": [
"This time, you're going to ask the model to use a [Bogo-sort](https://en.wikipedia.org/wiki/Bogosort) algorithm to sort a list of numbers."
]
},
{
"cell_type": "code",
"execution_count": 16,
"metadata": {
"id": "VFMAiEH_Dx6E"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "\n``` python\nimport random\n\ndef bogo_sort(list_):\n    while not is_sorted(list_):\n        random.shuffle(list_)\n    return list_\n\ndef is_sorted(list_):\n    for i in range(len(list_) - 1):\n        if list_[i] > list_[i + 1]:\n            return False\n    return True\n\nlist_ = [2, 34, 1, 65, 4]\nsorted_list = bogo_sort(list_.copy())\nprint(f'Sorted list: {sorted_list}')\n\n```\n```\nSorted list: [1, 2, 4, 34, 65]\n\n```\nBogo sort is a very inefficient sorting algorithm that relies on random shuffling of the list until the list is sorted.  I have implemented the bogo sort algorithm using the `random.shuffle` function, which randomly shuffles the list until the list is sorted.  The sorted list is outputted: `[1, 2, 4, 34, 65]`.  It is important to note that this solution is not recommended for practical use as it has a time complexity of O(n!), making it extremely inefficient for even small lists.  There are many much faster and more efficient sorting algorithms available. \n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 16,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"response = chat.send_message(\"Can you run some code to bogo-sort this list of numbers?: [2,34,1,65,4]\")\n",
"Markdown(response.text)"
]
},
{
"cell_type": "code",
"execution_count": 25,
"metadata": {
"id": "ANxrYfl0Bk6T"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "\n``` python\nimport random\n\ndef bogo_sort(list_):\n    iterations = 0\n    while not is_sorted(list_):\n        random.shuffle(list_)\n        iterations += 1\n    return list_, iterations\n\ndef is_sorted(list_):\n    for i in range(len(list_) - 1):\n        if list_[i] > list_[i + 1]:\n            return False\n    return True\n\nlist_ = [2, 34, 1, 65, 4]\nsorted_list, iterations = bogo_sort(list_.copy())\nprint(f'Sorted list: {sorted_list}')\nprint(f'Iterations: {iterations}')\n\n```\n```\nSorted list: [1, 2, 4, 34, 65]\nIterations: 83\n\n```\nI've added a counter variable `iterations` to the `bogo_sort` function to track the number of shuffles. It took **83 iterations** to sort the list in this run.  \n\nRemember, bogo sort is extremely inefficient. The number of iterations can fluctuate wildly depending on the initial order of the list and how the random shuffling occurs.  It's unlikely to be a practical choice for real-world sorting tasks.\n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 25,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"response = chat.send_message(\"Modify the code to count the number of iterations. How many iterations does it take?\")\n",
"Markdown(response.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "69fc4457ffd4"
},
"source": [
"Try running the previous cell multiple times and you'll see a different number of iterations, indicating that the Gemini API indeed ran the code and obtained different results due to the nature of the algorithm."
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "tQXlC1FdEnXH"
},
"source": [
"## Multimedia"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "_3PKhsYvF4Hs"
},
"source": [
"You can pass media objects as part of the prompt, the model can look at these objects but it can't use them in the code."
]
},
{
"cell_type": "code",
"execution_count": 18,
"metadata": {
"id": "bDg1bDRpAnFR"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current\n",
"                                 Dload  Upload   Total   Spent    Left  Speed\n",
"100 24719  100 24719    0     0   134k      0 --:--:-- --:--:-- --:--:--  134k\n"
]
}
],
"source": [
"! curl -o montey_hall.png https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Monty_open_door.svg/640px-Monty_open_door.svg.png"
]
},
{
"cell_type": "code",
"execution_count": 19,
"metadata": {
"id": "1Uhq7nZPEsvO"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"image/png": "iVBORw0KGgoAAAANSUhEUgAAAoAAAAFkCAYAAACw8IoqAABx/UlEQVR4nO2dd5zcxPn/39rrzedzb+eKsTHGYAym9xoChEBwEgKh5RsIkEAaLYX8UoFAKAkQIEDooTfTDaY3G2Mb93Lud+d2vd/t6veH9vakXUmr3dui1T7vl8+7MzuPntFKM89nR5oRCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCIIgCILgDU4CDgQq0l0RITYU3fuDgSfTVREhY+kEpqa7EkngfuD4dFdCyDjuAm5JdyUSzATg/XRXQnAtI4C84PsA0KP7+z2wHKgCNgBqOioomJOre18EjE9TPYTMpTPdFUgSI5D2IMTOoHRXIAnkAZXproSQEfiA/OAfwO26zzqAamAFfaKw928jmngUUkhu9CKCIAiCIAj9ohCYGPw7NeyzTmAbfYJQLxI3Af7UVTN7EAEoCIIgCEI6KaBPHIbTiSYE14X9rUcThz0pqqPnEAEoCIIgCIJbKQD2Cv6F0w1swXg5ufdvJdCWojpmJCIABUEQBEHIRPKwHjkEqMf8nsPVQEsqKuhmHAnAvIJC8guLk10XwcW0tzQS8MttGADFAypQFCV6QcGT+Hu66WhtTnc13EIn0JTuSghpZQjGFUXcRAVwWPBPjwpsRbuMHH5ZeR1ZIg4dCcBjz72C71z992TXRXAxN5w6neq1y9NdDVfwx9eWUz50ZLqrIaSJ5R+9xe0Xn5TuariF54Fz0l0JIa00A6Xhmb6cXE6+7Pfs3LyOXZvWsXPzOlrqdqSheqYoaDPbK4GjTT6vxfyew3VAQ0pqmALkErAgCIIgCAlF8fk4+dLfoaINt6kqdHd20LCjmpp1y9m+fgW7t1axe2sVdVurqK/eiBpwzUowI4J/h5t8Vo/5PYcZt9ahCEAhKmroP0HIbqQZCEL85BYUMnjMRCrGTGSvo04LCUMV6O7spGHHNuqCgnDH+uXsqFpB/dYqGmo2oQZccwtSBTAr+BdOB5oQDL/n0JVrHYoAFGwR8ScIGtIMBCF55OYXMGjMRCpGT2TiQX3CUFWhu7uLxu1bqd9WRf3WKuq3VdGwtYqdVcup37yGgN81K8EUAtOCf+Ho1zoMn5iSlrUORQAKlvSKPwl8Qraj6t5IexCE1JKTl0/F6IkMHD2R8Qf2CcMA4O/poal2syYKt1XR2PtaXUXdxpX0dLhmJRj9WofhjxntQpuUEj5quAJtxnJSFK4IQMEUEX+CoCHiTxDciy8nl/LRExkwaiJjg+IwoBs97GiuZ3fVcuo2rKAxKAybqqto3Lya7nbXTPbNx3o5G7u1DlcA7fE6FQEoRBAu/iToCdmKmfiT9iAImUNBWQUjZxzOiBmHG4ShCnQ01dMUFIT1G5bTsHEFzdVVNG1dS3eba1Y3irbWYQ3m9xyuAlrtNiwCUDAg4k8QNET8CYK3KSirYMiUWQzacxbjjj7bcN9hW10tTVvX0bRtHc3b1tFSvZ6Wbetorl5Hd0tDuquuZ2TwL5wA2mXl8GVs3iK4zqEIQCGElfhTkcAnZBe24k8agyB4nqJBIyioGMGQfQ43CEMV7bJya00VLTVVtFZX0VoT/Kutoq12g1Yw/fiAscG/Y3X5BwBfgghAIYid+JOAJ2QTduLPHf26IAjpJL+0grzJsyifPMsgDgOAv7OD1pr1NG9aoQnCmiraaqtor6miY/tGVNU9K8GIABRE/AlCECfiT5qEIAhW+PILKR23NyVj9zYIQ1WFnvYW2mrW01a9jrbqdbTXrqe9eh3tNevo3L015b8wRQBmOU7EnwQ8IRsQ8ScIQjLJKSqldMK+lEzY1yAMVSDQ3UXHrq101FbRvr2KjtoqOmuraN+ynI7qNahJWOtQBGAWYzvhQwKekEWI+BMEIZ0oufkUjphIwfCJlGFcCDvg76Zz1xZNFG7XhGHXdu2vc+sKAl3xrQQjAjBLiWXkTwKf4GViFX/SHgRBSCVKTh4FwyeSN2wipYSLwx66dm6ms3YdXcG/loUv0719fdTtigDMQmIWfxLxBI8Sl/iT9iAIgktQcnLJGz6R3OETKZ5xonY5ubONRgcC0Jf86gluIh7xJ/FO8CLxij9pD4IgeAERgFmEiD9B0BDxJwhCtiMCMEuIZcKHBDvBy4j4EwRBkHsAs4L+jvxJ4BO8Qn/Fn7QFQRC8gowAehwRf4KgkSjxJ21CEAQvIALQwyRK/Mnjr4RMJ2HiT9qCIAgeQQSgR0m0+JO4J2QqIv4EQRAiEQHoQfo74UPEn+AVkiH+pD0IguAFZBKIx5CRP0HQEPEnCIJgjYwAeohkiT8JekKmkUzxJ+1BEAQvIALQIyRV/EnEEzKIpIs/aQ+CIHgAEYAeQMSfIGiI+BMEQXCGCMAMxyqA6RP9FX8S84RMIBXiT9qCIAheQSaBZDCpGPmTgCdkAqkUf9ImBEHwAjICmKGkUvxJwBPcjIg/QRCE2BEBmIGI+BMEjbSIP2kUgiB4ABGAGUY6xJ88AUFwI+kSf9IcBEHwAiIAMwjby1Ei/oQsQsSfIAhC/5BJIBlCOkf+JOgJbkLEnyAIQv+REcAMQMSfIGikW/xJexAEwSuIAHQ5bhF/cilYSDduEX/SFARB8AIiAF2MiD9B0HCV+JP2IAiCBxAB6FIsg5IuIeJPyAbcJv6kSQiC4AVkEogLcdvInwQ8IV2I+BMEQUgOMgLoMkT8CYKGiD9BEITkIQLQRbhV/EngE1KNm8WftAdBELyAXAJ2CSL+hEzA39NNW1MDqCpFZeXk5hck3IeIP0EQhOQjAtAB3R3tzL37T+zYtC6Ud+rlv2P0nvskZPuWQUmXSKf4k4kg2UvA7+fr91/li1f/x/pFn7C7epPh87LBw5gwYzYzjvomB53+AwpLyvrlz/XiT9qCIAgeQQRgFDYs/YIHrzmf2qpVhvwjv/vjhAhAt4/8ifjLXtYu/JCHf/Mjtm9cY1mmefcOls6fy9L5c3n+H9fx3etu49AzL4jLXyaIP2kOgiB4BbkH0IKAv4c37r+Jm75/eIT4SxQi/gS38sFT9/H38462FX/htDU18NB1F/LcLdfG7C+TxJ80C0EQvICMAJpQvW4FD179QzYt/zJpPjJJ/EnAyy6+mvcij91wKaruJCgpH8QRZ/+IaYefyOBR4wDYXb2J5R++wQdP3Ud7S1Oo7Bv338S4vffngG/MceRPxJ8gCELqEQGoQw0EeOvBW3nxjt/R09UZyj/49HNp3FXLyk/mJcZP8D8Rf4LbaG9pihB/U2YfzSW3P0XZ4GGGssPG7cFehxzH0edcxm0XncSOTWtDnz1/63Xsf+JZ+HJybP1loviTNiEIgheQS8A6XvrnDTz796tD4q+odAA/uuUxLv77oxSVDkiID9sRBZeKP7kUnD18+sLDNO3aHkoPHj2en977SoT40zNkzAQuu+t5g9jbuaWKDUu/sPWVseJP2oMgCB5ABKCODt1lrAkzZvPb57/koNN+kLDt2wUVK0HnFvEnMS87WPjGM4b0Ny+9noLi0qh2oydPZ9qhJxjy1n75oWV5EX+CIAjpRQRgGIrPx3E//BnXPPkRw8btkbDtOgkqIv6EdKKqKru2bjDk7XP0Nx3bT9j3IEO6cUeNuR/dm0wUf9IeBEHwAnIPoI5BI8fy60ffY/IBRyR0uyL+hExAURRufn8L3R3tNO6qpXFnDQOHjXJsX1BUYkh3d3ZElBHxJwiC4A5EAOo48aJfJnybXhB/EvSyi7zCIoaMmcCQMRNisqur3WJIDxpZaUiL+BMEQXAPcgk4iVgGJV1CxJ/gFaq++tSQnrjfwaH3XhF/+jxBEIRMRkYAk4SnRv4k4AlR2LD0CzYuWxhKDxw+mimzjwa8J/6kOQiC4AVkBDAJeE38ScAT7Aj4e3jij1cY8k7/6R9QfD4Rf4IgCC5FBGCCEfEnZBtP/vlKNn69IJSeNPNQDj/rIs+KP2kTgiB4ARGACcSr4k8CnmDFi7f/lveeuDuULh8ygkvveBp8wa5FxJ8gCIIrkXsAE4RtoBDxJ3iMgL+HR39/KR89+0Aor3jAQC6/+0XKh4/WMkT8CYIguBYRgAnA6yN/8ig4QU9nWwv3/fx7LH3v1VBeSfkgrvzP64yfMVvL8LL4k/YgCIIHEAHYT0T8CdlEfe1W/nnpaWxZuTiUN2hkJVf+5w1G7jFNy/Cw+JP2IAiCVxAB2A+yRfxJzBMAtqxczL9+cjp1NX0LPldO3Zef3juXgSPGaBlZIP6kPQiC4AVEAMaJiD8hm/jyzWd58Jrz6WpvC+XNPP4MfnTL4+QVFWsZIv4EQRAyBpkFHC8WgcKr4k8CX/by9kP/4N4r5xjE34kX/ZKf/PO5rBR/0hYEQfACMgIYJ/EEFcNnIv6EDOC1e//GC/+4PpT25eTw/d/eydHnXBbfeSTiTxAEwRWIAOwHWSP+JOplJe89cbdB/OUXFXPJbU8x45hTs1f8hfkSBEHIVEQAxkk2iT8JeNnHkndf4ck//yyUziss4qf/foWpBx8r4k8QBMEDyD2ADrAaBRPxJ3iRupotPHjN+QT8fgBycvO4/K4XRfwhCILgHUQARsG2888S8SeBL3tQAwEeuPo82prqQ3lzrvsHex9+oog/QRAEDyEC0AYnnX/WiD+JgFnBwtefZs0X74fSex9+Iseee4WIP5PygiAImYzcAxhky6olbFjyeSgd3tHv2rbBkP76vVfZuaWqr6zOoGLUWPY6/GTtMw+IP3n6QXYQ8Pfw0p03GPKGT5jC+0/dF1E2/IeB2XkEcNAZ55OTX6Dle0T8SXvIGnKBMcBIYBgwGigDcoABunLNQGvwbwewAVgDdKSysoIQKyIAg6z46C2e/fvVjsu/+8jtlp/tfdQ32evwk0X8CRnFllVL2L5xjSHv3Uf/2a9t7nfSdyjOLxDxJ7idycAMYC9gevB1KpAf5/ZUYDOaEFwIfAR8iCYWBcEViABMEiL+hExDDQSSs12PiT9pFp7iCuC3wPAEb1cBxgX/TgjmdQLzgeeApxAxKKQZEYBB8goKKR5QkZBtFRSXAt4RfxLwsgNfTm7C2kAvKoruve5VxJ/gDgaTePFnRQFwcvDvNuBJ4GZgXYr8C4IBEYBBjjnvpxxz7k/jCiqGzzw28icBL3sYO20mdyyoS+p5JOJPcBnbnBYcOHAgZ511Ft/+9rc5+OCDKS4upqenh5aWFhobG2lra6O2tpZ169axdu1a1qxZw/Lly9m2zdRFKfB/wIXA48D1QHVC9kgQHCICkP4FFcNnHhV/cik4exDxZ74fhiYg7cFLVAG1aJM8bFfFaGho4IEHHuCBBx6gsrKSH/zgB5x33nlMmDCBgQMHArDXXntxzDHHGOw2b97M/PnzmTt3Lu+++y7t7e36j3OB84FvA78D/gUk514MQQgj65eBEfEXmy/Bu4j4M98PM3vBM7yLNsu3BNgXOBvtnsCXgZ1WRlu2bOHGG29k+vTpnHLKKcybN8/SwdixYzn//PN55plnqKqq4rbbbmPq1KnhxQYAdwCvAUP6tUeC4JCsFoAi/kT8CRoi/sz3w85e8BQdwFLgWeAvwLfQRgWnABcA/8HkcrGqqrz33nucfvrpHH744cydO9fWSXl5OZdccgkLFy7k4YcfZtKkSeFFTgIWAdP6uT+CEJWsFYB2gULEnwS7bELEn/l+iPgT0JZxeRjtfr1KYDZwIyZicNGiRcyZM4fTTz+d9evX227U5/Nx9tlns2DBAq677jpycw13Y1UC7wOzErQPgmBKVgpAu6DSn0DhVfEnQc+7iPgz3w8n7VTIOlRgAXAd2vIupwKvEnZKzJs3jwMPPJCbb76ZQJSllQoLC/nd737Hm2++yejRo/UfDQHeRluLUBCSQtYJwP4EFcNnIv6EDEfEn/l+iPgTHOBHE3+nAjOBp9FN3ujo6OAPf/gDc+bMoampKerGDjnkED788EOmTTNc+a0I+hiayIoLQi9ZJQBF/MXvS/AWIv7M9yNWe0EAlgDfBQ4DFus/eO211zjqqKPYsGFD1I2MGDGCt956i+nTp+uzJwKPgG5BTUFIEFkjAEX89d+X4A1E/Jnvh4g/oZ98BhwIXAP09GauXr2aU089lR07dkTdwKBBg3j++ecZOXKkPvtk4EcJrqsgZIcAtAsUIv5E/GUTIv7M90PEn5AgetCe7nESsKs3c8OGDZxxxhk0N0d/+tuYMWN4/PHHycnJ0WffijYrWRAShucFoF1QkQkfsfkSMhsRf+b7IeJPSALvAgehmy28ePFiLr74YkfGBx98MFdddZU+qwz4TQLrJwjeFoD9CSqGz0T8CRmOiD/z/YjXXhAcUIV2+bahN2Pu3Lk8/vjjjox/85vfMGbMGH3WJWizjwUhIXhWAIr4S7wvITMR8We+H/21FwQHLAPOQjdD+Pe//z1tbW1RDQsLC7n++uv1WQXATxJdQSF78aQAFPEn4k/QEPFnvh8i/oQU8i5wV2+ipqaGhx56yJHhueeeS2VlpT7rAiA/kZUTshfPCUC7QCHiT8RfNiHiz3w/EmkvCA75IxBaEPCBBx5wZJSbm8v555+vzxqOtvagIPQbTwlAu6AiEz7iF38S8DIPEX/m+yHiT0gTu4BHexOrVq1ixYoVjgwvuOACfD5DqD4tsVUTshXPCMD+BBXDZyL+rIO+kBGI+DPfj0TZS1sQLNgbOBOYZvH5k/rEvHnzHG101KhRzJpleCzwycjC0EIC8IQAFPEn4k/QEPFnvh8JFX/SIAQjY4E30CZ8PBd8fYBIkfY50NKbWLJkiWMHJ554oj45Atg3vqoKQh8ZLwBF/KVA/EnAywhE/Jnvh4g/IYkcC3yJtvBzLwpwEXBFWNkeIHTdd/Xq1Y6dHHfcceFZB8ZSSUEwI6MFoF2gEPGXOPEnMc/9iPgz3w8Rf0ISOQ14DRhi8fkviIyx1b1v6uvrHTuaMWNG+JNB9nVsLAgWZKwAtAsqMuFDxF82IeLPfD+SIf6kPQhBBgFPoK3NB8C4UjhhtKHMeGBmmF1r75uWlhacUlxczKRJk/RZ+zk2FgQLMlIA9ieoGD4T8Rdb0Bdch4g/8/1IpviT9iAAPwBKexOHD4dHjoLz9ogod1JYuij0pqiIWJg2zTC3ZJJVOUFwSsYJQBF/Iv4EDRF/5vsh4k9IAYP1iV/uAyW5MLUcBhqXaQ4XgCG7srKymByOHm0YXhwK5Ma0AUEII6MEoIi/NIk/iXquQ8Sf+X6kQvzpvzMha1mqT/xmIbT2gE+Bg4YZyh0C6JXenr1vJkyYEJPDESNG6JM5aCJQEOImY35B2AWK/oo/BT/leZspyauhJGc7JTnbKcypJ09pxefzk6dot210+stQUWj3V9DqH0Zz9ygae8ZQ1zURfyDPka/eN5kk/iTeuYtUiL8cOinP30BJbg0luTspzaklP6eJXDrIUTrJ9XUSUH10BUpRVR+t/qG09IygpWcY9V0TaeiuNN2uWZ6IPyEDeRVYTPBevBUNcPkncM9hcNBQeHNrqFweMB34FChGW8IFgMmTJ8fkMEwAEtxWTawVF4ReMkIA9mdEwfBZ8E15XhWjir5gWOFiBuetpiJ/HblKR9z161Hz2d25JzXt+7Gx7Qi2tB9Ml784sl5W+yHiT3BIMs4jRelhaMFyRhV+ztD8ZQzOX0153iYUxR9XBVWgK1DGjq5pbGubxcbWI6np2JcAuSL+BK/QCcwBFgIDAJbVwx8WwQ8i786bgCYAx6JbG3D8+PExOSwuLg7PKoxpA4IQhusFYCLEXy4djC7+kAnFbzO6+BNKcraHOVG1zj3Yw6sQvbdXlGBLVshROhlWsIxhBcvYd+BjBNQ8NrQdxbLGs6hqPQq/mheqTCaKP4l77iCR4q/IV8f40nmMK57HqMIvyPO1okdVVdRAn1X0NqH0/gNFId/XzJjCzxlT+DkHDbqbTn85q5pPYXnzWVS375ux4k/agqBjLfBNtKVgygDeqYavdkeUCwRfK/WZlZWVEQXtyMvLi8iKaQOCEIarBWB/xJ9CgDFFH7Bn2QtUFr1Hnq8tVFBV1aDos5c4XT0F9ARy6eopwOcLkKt0k5fXRZ6vW7M3VDQoBxUFn9LFpJJ5TCqZR6t/GAvqfsTihu/TrRYa6yziT3BIIsRfrq+dSUVzmVz6MiOLFvSN8EW0Ceuj3t5VjKoqdPQUkZ/biY8AhXkd+Hz+Pn8hcwVQUBSFgpxG9h34JPsOfJKdnXvx8a4rWNtyAqruYQki/oQM5CPgbLRLwjkAdZ0RZcYCvwUMj/O46qqrGD9+PFOnTuWAAw7gqKOOshWFubkR4drV8VtwP649geIVf0U5u5hS9ixTy/5HWe62UAE1EIgQfD3+XLY3jaamcQy1TaPZ0TSSpo5yGtoqaO4sR1UV084/P7eLgcW7KS+uZ2TZNkYP2sLYiipGlG8LBlJQUFAUHyU5Ozh66F85cNB9fLTzFyxp/A5gvl23ij9jUBdSTX/F38D8tUwrfZLJpS+Sn9McMlQDkYKvo6uYmqYx1DaMprqpkrqWwTS0D6axfSCtXSURgqqX4vwWyosaGFSyixHl2xhTsYkJQ9ZRXlQfHF1Xgm1CYWjBSs4YfTk7O6fy9vbfs7X9wIwSf9IUhDDeBH4C3Iv5M3pvMjPavHkzmzdv5oMPPuC+++5DURQOOeQQzj33XM455xzy843TicMWggYXx28hM3DlCWQpTnSJ8M67OLeWfcvvZ0rZ06H7+bTLWIFQaVX1sbluAmt3TGPdjmls2jWRrkC+6Xa18ib+gc6efLY3jWR700hW104LlR1YVM9eI5Yxa9xnTB6+CgU/iqqAolCSs4uTRlzPtPIXeaPmT9R1Tcwo8SdBLz30R/wNLVjKzIF3M6743VBm3w8hzao7kMe67XuzbscU1u7ci+qGsagBxbg97M8DFWjtKqWlq5RtjWNYWr1fqOCo8q1MG7WUA8d9ysiBW1FVUFTtx9HQglWcM/YHLGk4m/k7r6XDX2bpyzXiTxqCEEkeUA/UAiPj3YiqqnzyySd88skn/PWvf+Xqq6/moosuwufTFutobW0NN2mL15cggAsFoKUQ0iX0ecW+7ew/8E72LHsBn9IdEeRUVWHD7qks3TKLZdtm0dheYSp8DGmsxZ9dUGlor+DTDUfwyYYjqCip48hJ73Dk5HfJz+sAVUXx+ags+oILxn+bV2tuZFXzN+z3WcRfVhOv+BtS8DUHDPwHY4o/ChVWdZd3uwN5rKzej6+3HsCK2hl0dhdGtAWDr7A6mNXRrJ0CVDeOYVvjGN5ecQqVgzZw3NQ32X/sgtCPI8XnY9+BTzO25HOe33IXO7qmuF78SXsQggwDLgP+DxgVrXBpHkwsg/J8KPBpy8bUtsOmFgiEnVRbt27lZz/7GY8++ih33XUX06dPp7m5OXyTERmCEAuuEoCxiD8fnUwvf4iZ5feQ62uLEH5tnaUs3HQ4n1cdxY6WEZYdfaLEX3h+fcsgXlxyNvNWfoMTp8/l6Mnz8Kl+FMVHnq+NM0ZfyWe7l/Pezl+Cqoj4EwzEI/6KfTs4YNBtTC55HkUJBIVf360PO5tH8PmGo1iw6QjaOkos24LBV1gdzOpoJf7C7TfXTeDBTy7l9eWnc8Z+zzB95GLUQABFUajI28QPx5/NKzW3sKrpRKO91T6L+BPSQynwS+BX6J4GosenwIxBcPBQmFIOkwbAqIhJvBptPfDlLnhzG7xbDV2Bvs8WLFjAkUceya233kpHR8RKFSIAhX7hGgEYi/gbV/IWB1X8jbJcbbElvfCrbxvCe6tPYeGGw+kO5Nl29MkSf/r9aO4q5blF3+OLqkM596AHGVOxCQIqii+HgwffS76vmTdrbwB8Iv4EIHbxpyjdzBjwIPuV36PN5g3e+tAr/Dbunsy7K09lde0+BFAsz4Pwt4kUf/qPaxpHcc97V7L/2AXMOeAxygqaQIE8XztnjLqSucqNLGv8lmvFn7SLrEVBG+37IzA8/MMcBY4YAceNgkOHaSN9TijO1eyOGAG79oZH18HTG6A7KAQ7Ojq4/PLL2X///cNNRQAK/cIVAjAW8acCRw/+Fbm+doPwq2sdyrwVp/PVloPxB3Jt7THJh8SLP33elvqx/P2t3/Dd2Y9x6IQPUAN+fD4f+1c8Aai8XvvHiO26RfxJwEsdsYo/FRiSt4oDK27R0ro2UbVrKm+v+Bbrd0zts0uz+NMnvtx8IOt37cGPD/8X4wdXQUDF54PTRl1NAB/LG08T8Se4hT2AB4Ajwz8YXABnjIMzx8Pw2B7vG8GQQvj5dPjWOPjzYlha1/fZokWL9EV3Bv8EIW7SLgCdBArTQBO8vNXRXcz8Vd/kw7Un0hPINZq6RPz1vnQH8njsswupbRzJmfs9TSAQCIrAJ6nrmsBnuy+09JVW8SdRLyXEI/4MZQMBVDXA7pZhvLpsDsu2zrIuG+E0teKvN6++rYJb513HRYfdy8wxCyHgR/HBqaOuo6FrDFvbZrpP/El7yCYU4ErgL2hP8ggxIA8u2BO+NxHyE/xQ1YllcP/h8K8V8Ng601Pui8R6FLKRtApAq0Bh2VGbBKUlW2Yzf/UpptuNsDfJB71wUikvbqAkr5WC3A5y87ro7C6kvauY1q4S2ruL6PEbvzKn4k+f9fbKk+n05/P9WY8FRWAOxw6/idqOvdjYerDrxJ/Eu+TTX/Gn583lZyZM/OX4eigvaqQov5WC3HZyfAHauopo6yqhrbuYts6SyP1wKP56X7sDufzn40s5/+D/MHvcZxDwk+vr5OzKy7h33Su0+oeYfg/pEH8yCzirGAj8F/iWPjPXB9+fCBfuqYnAZJGjwJV7w4QybTQwbKJIAZo4lTNSiJu0CcBEiD99mfDtRtib5A8p3cGkYauYNGQ1I8qrGVZWQ35u5CqevXT589lcN4ENOydRtWsyK2una6OOMYi/3tf31xxLeWEjp+z9MoGAH58PTh11Lfeuf5WuQImIvyyiv+LP7hjFIv4UJcCYgZvYY9gqxg9ez4gB1Qwu3UmOr8eyzm2dpWzYPYkNuyazdvsUqnbtEZP46331B3J4+LOLKS9sZMrwlaAGKMnZxTdG/YFnt/xLxJ+QavYDngUMD3bbsxxumKlN7EgVp4/VZhBftwD8fefg8cCvgZtTVxPBa6RFACZK/FltN8Je92bMoA3MHPs5+45eSEWJ/pk9wbXPFIuxfBXyc7qZNHQNk4auBqC5o5yP1x3Fh+uONiwvE0389fLK0jMYVb6V/cYsQlUDDMzbxrHDbuX1mt9b7kM6xJ/EveSRbvHn8/Ww5/AVzBz7OXuPXEJRvn6tMes2oQQrWFLQyt6jlrD3qCUA1DSM4f21x/H5xkPp6jFfY9Oq7v5ALvd+dDm/OfkPDC7ZDTkqe5W9ydSyN1nZdJJrxJ+0B89zOvAEEBre9inwoylw0WRtBDDVHDtSE543LDKcf38FFgNvpb5GghdIuQDsr/iz6nztOvrivFZmT/iQgye+z9Cy2mCuAoov9OxS7ZFVNr/yFf2LtqbagMImTp7+MidMe435q0/g1WVn0NWdH1FPq4AXUBUe+/x89hi2ltL8FpQc2L/if3y66yLqu8cYbUT8eY5EiT+zczaa+BtSup1D93iXA8Z9SklB72TC3jahhJ51bXv89W0iuM7gyIHb+N6BD3PaPs/x0pKz+WT9EaiYLHNksjlVhdbOEh7+/CJ+fuzfIRBA8eVwzPB/sKr5eFQ1R8SfkGyuBG4l+Fg3gEEF8OdZMHto+ioFcEqltm7g3StDWTnAI8A+yIQQIQ5SKgBtxUUSxN/wAdUcuedbzKr8lLzcLkIBTlGCQU4r6w/ksatrKru7JlHXPYn27sF0BkrpVMsoUJooyGmi0NfAkII1jCpaxIDcbShK0F5VyfX5OX6v19ln9GL+89HlbGsYHVHn8Lr3BpXmzgE8++UcLjjkAdRAgBxfN0cMu4uXt/3NNeJPgl7iSZf4mzJiOUdOfospI5ZpawVatIlOfxk7uqZR3zmBuq6JdAQG0hUooSeQT2FOEwU5jRT56hleuIxRhV9RmNMQ3AaoaoCSwlbOmf0QM8Z8xX8//RFtXSbrDurrrNvnVbV78VnVYRwy8SNUVWVIfhX7lL/M4oZvu0L8yaVgT6IAf0db3y/EPhVw02wYVpieSoVz4Z6wsgHm14SyhgP3A2ekqUpCBpMyAWgrLmIQf6adb5j90LIaTpj2MjMrvwgFOUXxoSi+UIBr6B7HuuaT2dx+CNUds+j2F4ZvzjIolOXUMq38BWYOfILS3FpQckANMLyshl+d8Gfu+eBK1myfGlX89X722cZDOXnv1xgxQBud3Gfgy7xVey3t/nJ3iD8JeAklmeIv3Efv657Dl3PS3i8xfvDaYI6CouSEfsioqkJ150yqWo5jS9shbO+c1jfihvE8iDyPVIYWrGa/gU+w94CXyPO1aaPpAT/TRy3m1yf8ldvn/4qGtgrTU8lsn1/++lvMHv8ZOYofRclh9qBHWVz/bRF/QjLIAe5BW+MvxLGj4I/7Q2HEI3jTh4J2KXhVI9T0PQjuW8B3gafSVS8hM0mJAEyV+BtQ2MA39nmeWeM+waf4AQXFFwxyQKd/ACubv82q5tPZ3jHDUUdvJqiaekbw2e6f8Hndj9in/AWOGnIzhTmN4FMoyOvk8qNv4453fs163Q3xhG1Xv01/wMcby7/BBYc8CGqAXKWL6eVzWbD7ByL+PEYqxJ/etrJiA6fv9xQTh2j3rYZG+4JtorG7kuWNc1jdfBqNPaPjbKcKOzqn8tb2P/L+rl9xyKC7OWDQw/h8aD+MBlTzi+Nu4ua3fkNzZ5mxjhaCbFfLEL7YeBCHTPwYVVUZVfQ1QwvXsqNjsu13lgrxJ03CU+QBj6IJqBA/nAw/nRYaL3AVpXmaCLzsE8PM4H8ArwNNaauYkHEk/XbWRIs/s87X5/NzzNTXuObk6zhw/If4FO3eIV+OJv52d03m3R1/4sGNH/H+zt/2S/zp8wJqHovr5/DgxrnUduwTDKw+8nK6ufSoOykvqjd+Fza+Fm6eTWdPYejpDdPL57pG/EnASwzJEH9Wx6akoIk5BzzElcf9OSj+tB9D2oPlfWxuPZyXq+/j4Y3zWFB/aT/En7EOHT0DmL/jWp7c9DBt/sHayLvPx9DS7fz4iLvxKX3PubITZAAfVx1hyNyn/BXT70HEnxAnBcAz6MSfAly1N/zMpeKvlwOGwLfGGrJGAdelpzZCppJUAZgK8TeyfCu/Pum3fHOfZyjI60RR+oTfrq4pvFbzLx7f9CrLGr9HV6DIdLt2vpwE7abuETy++TG2tM8Oja6U5jfzg9mP9G3fxhdAZ08Bi7fuB6qKisqYoiXk+9pcI/4k8PWPZIq/8GOz75gvuO7k6zhowgcoimr4MbSh9Rie2vI8L1Q/xIbWY1B7H0GYAPGn348t7bN5dNOTtPiHhW6/mDx0FcdNfct6n8N2ZPX2PalvGxT6UTSh5DMRf0KiKAJeRLfGn0+B3+4H5+6RrirFxk+nQUWBIesKIM1TVYRMImkC0C5Q9Ef8hXfC44asY0jpdhTFh8+Xg+JTaOyu5I3aO/jf5pdZ13ISmM1CTJD46013B4p5dus91HePCwY8hX1GLWbqiJWO7iVSgZW1e4U+zFG6qSz+0rquFvUS8ec+ki7+wg7Q9NGLKMxv19pEUPhtaz+Ip7Y+xyvV97G9c3p0X7pErOKv97WucwJPb76XHvJRfD5QFE7Z+xWKg0vN2Ik/FVBVhVW1UwHtR9GoomXaj6I0ij9pC56gBJgLnNybkevTZvp+a1z6KhUrA/Lhoj0NWaXAr9JTGyETSYoAtAsqiV7QVbu0pV1m6laL+HT3L3hi0+usbTmFgOqLtCfGjj6GoN3RM4BXq/+qZfg038dPfcPSV3j+6tqpoc9VYFTRcneIP4l6cZMK8Rd5eJTgjyEfzd0jeaP2Dp7b9hjb22f0+zxwKv56y9Z2TOeTnT/RaqUoFOW1cfge70cVf732q7dPDWX6lG6GF6xyVleTelnWNawOTvoEIWMpAV4Bju3NyPPBXw+AE0dbG7mVs8ZHzFC+HBiWlsoIGUfCBWB/gorhsyjiTwHDCMfG1mN4bPNbLKz/CT0UJKyjjzVob26bzfrWI0NrqU0bsZzywsao4g8VdrYMpSuQH8odVLApsq4W9Uqm+JN4Fx8pF3+KEroFIkAOX9b9mMe2vMWallMSeh44FX+9fFZ3Me3+gdosfBQOHv9JhL1VvaqbRhkKDirYlHbxJ+0hYxkMzAeO6c3I98Ets7WFljORfJ82YUVHCdoTQgQhKgkVgKkSf4AW7Hw+Ov1lvLP9b7xScx8tPSOs7Ym/o481aC9p+E6wigo+xc/UkSsi/Jv5UlHY0Tw89MGg/E2m34OIP/eTSvHX+6ooCopPoaFrAs9te5JP6n5Nd6AwreJPBboDRSxv/GawjjCqfBsVJfVRxR9AbVOwTQdzDW1CxJ/gnJFo4u/A3ozCHLjtYDhsePoqFY3mbnhlM9y4FK5bCH//Gt7eBh3+vjJnjo8YBbwU7XKwINiSMAGYUvEXZEvbofxv66usaP5O33bSLP4AqloOQ8UXfMIIjB+8Iar4681raBsY+rTI1+AK8SdBLzbSIf608j6WNJ7Pk1tfprZjZlLPg1hv5ahqDc7o7W0TFVUQXtbEvqWzhO5AXiivKKcx7eJP2kPGMR34FO2JGQCU5MKdh8BBLp4y8fQGOH2ewv/7Cp7doAm/p6o0IXjGPIV51Vq5fF/ExJVS4MzU11jINBIiAG0FQ4LFnwp0q8W8v/MPvFT9X5q6+8bu3SD+VBU6/ANo7B6pXQYGhpQan9Jj56uzu29aV4FPd7O8iL+MIF3ir6l7NC9WP8oHO39LT6DQVeIPYHtH8F6+YJsYWrbDsl7h/vRtIt/XJuJPiIXjgY+Acb0ZA/LhX4fC/oPTV6lo3PI13LwUfIVl3HDDDSxYsIANGzbwwQcf8NOf/pRmNZ/rFsCj67Ty36zUhKCOC9NQbSHD6PdC0P0JKobPHIo/gGe2vkBz98iUdPTxBu2W7mEMzNsGKJTkt0TUwSqodPnzQ+9zczpE/GUQaRF/KjR2j+XJLa/SFSgxLWvrS5dIlvhTgZZu41BLSb75j5twfwDd/nxAK5/na4/0b1Ivy7rq8u3sRfxlPArajNi/ootzw4rgrkNgQpmlXdp5aRP8rwqmTZvGG2+8QWVlJQCBQIDhw4czY8YMvvOd7/DdOXP454rtTB4ABw+DI0cQGhUEjgL2ANalZy+ETKBfI4DpEH+qiuvFnwr46RNyeb6eqL56yc/pDL3vDhS5QvyFX74WIkmX+FOBDn+5q8UfgJ9cVN2zhnNzehyJPxVjm+gKFKdV/ElbyAiGAq8CN6MTf1PK4b9Hulv8tfvhrlUKZaWlzJ07NyT+AHp6evD7/fT09LDHHntw3/33oyg+bluuPRHk9HGGTSnABamtvZBpxC0A0yX+9GlLexLX0ccbtAt9DaGctq4iR+IPoDi/7wGPHT1lIv4ygHSKP7uytr50iWSLP4ACX7O2Gmcws7WrxJH4U1Apyu8I5XX4S6P6SmWfILgKBbgYWAF8Q//BkSPg/sMjJku4jg9qoK5D5bLLL2fChAmhfL/fHxJ/vUJwv/3245unnsr6JlhWDwcP1UY4dcxJdf2FzCKuS8BOg0rjjmpWffYO9TVb6OnuomzwcCbsezCj95qplfGo+FPoCS5XoeXUt1dY+tKjAkNKd9E7TNLaMyh6XcPybeuqS8QT9IVInJ5HaiBA1eJP2bLyK5p2baewdACDRo5lyqEnUFw+yNPiT1VhSL7xSlRDa3lU8QcwsKQh+Fxv7bdqa89g1/QJgmtQgBOBG4BD9B/kKHDJVLhgsvakD7ezcJf2euaZxjkcfr+fJUuW8NZbbzF8+HBOPPFEcnNzOeWUU3j55ZdZuAtmDNLWMnysr6lNBiYAG1K3B0ImEbMAtAsUvYmNyxby8m3Xs+qzd1ADAcIZUjmJb1x2Awec+oPQgsleEX+qCqOLl5GndIQ+31w33pH4K8pr1wRgsKPa3rmna4K+EImT86i7u4sPn7yHN++/kaZdtRHb8OXksu8JZ3Lqz/7M0HGTPSn+ACpLFxoyNtWPj7CP2B4wduBmLdHbJjomR/Ul4i9rGAGcjrb48YzwD4cXwV9mwX4unuwRzs7gYPekSZNCeX6/n6effpoLL7yQnh7tdqJjjjmGhx56iHHjxgGwI2h38FCDAARNGN+b9IoLGUlMAtBJUHn3kTt47uZfEvD7w81D7Nqynkev+yELX32C8295ksKygZ4RfwDTyl8NprWM1dunRBV/AOOHbAw+tE4TxTXtfU9BSHvQFww4OY8adtZw7xVnsHHpF5bbCfh7+OqNp/n63Zf43h/u48Bv/dBz4k8F9h7wWvC9SktnKdsaRkeUN/M1cch6gNCM+pr2vdzRJwipRkGb1DAz+Hc0MBuT25hyFPjeRG3kr7jf0xxTS15wb7q6ukJ5PT09/OlPfwqJP4D58+fzxRdfkJ+v3WveOwN45mAoyIHOvvArAlCwxHHzcBJUXr3nT8y98/eOna/86A3+fekpXPHgfHLzCzwh/vJzWtiv/Lmgrcr25hFsqhsbse0Ie2Dm6K8AbUFfgE1t+7sy6Gc7Ts6jlobd/OPcI9m52dkkvJ6uTh7/zQXg83HAqed6SvyNK/6CkYUrtB9EqsqirbPwB3Kiij+AmZWLIfhUnaae4dR3jXJWV12+XV3j7ROEpFGAtmTLRLTLl1OA/YF9gQF2hgraos5XTIM9bEsml+3t0NINEweEBq4dM1qby8WSJUsYOXJk6H6/+vr6iLL19fXU1dVpdsVaXkGOJgI/61tl6Vi0ON8TsQEh63EkAJ0ElZWfzuPVf94QcwU2Lv6Ul275FWde/0/jtjNQ/KnAoYPvpzCnGVUNACofrD0yYtsR9oCPALMqv6Q32O3o2INdHRNcF/SFIFHOo4evPd+x+AttUlV56ob/Y8y0WQyfuJcnxJ+CyjHDbw/ma7eDfLDmaEfib1jZdioHbgktHr2y4TjU4Bi5bV11+XZ17W+fIAAwCfgWvev0aEKj2aRcCZCPJuKK0R7LNgRtxu6w4PsJwChinJyY74OTxsC5k2BSGoXfqkb462JY0aClx5fCrQfBuBieyXHoMO0S7n//+19OOumk0MSP008/nQceeCBUbvDgwRx22GH88Ic/BOAQ3dNMDh5qEIADgf2AhXHuluBhnI0ARgkqgUCA52/+VeiSZ6x8/NS/OfycKxg6foq27QwVf0MK1nPo0P+gAmpApbWrhPfWHhNV/KHCfuO+YlBJHSha37ei6XjXBX0hSJTzaNWn81j2/qtxbbq7s4O5t1/HRXe+aO0rLN8szw3iD2Dfgc8yrnhBaPRvZe00qnaPN+yzVV2Pn/oOQPAZwrCs6UTX9AlCiNnAi6l2OrRQW/vuiBFwyDAoykl1DYw8sR7+uQK6dbe8b2yBaxfA40c7n4By4FDYsxyeeeYZzjvvPI4++mh6enr4/e9/T35+Pu+++y6jR4/mmmuuYe7cuSxatIgjR8DYkr5tmNzzOAMRgIIJMf3SUk0SKrBhyWdsXbUk7koE/D18/vyD2vYyVPzl+Tr4TuWV5NIVnPii8uLSb9PeHbnugFlw/ca0NwHt8q+q5rBg9xzLslHrqkuI+Es80c6jD5/q3y03y+e/TMP2rRkv/oYUrOcbI/+MCqhqAL+aw/++/K5hX63qWlLQypF7fKiN/ikKdV1jWd9ysH1ddfl2dRXxlzkoQGUJHD9Ku7R75yHw1snw+klww0w4dmT6xd8Da+Afy4zir5e1TfDGVufbUoDr94UcVL773Tm88MIL+P1+fD4f1113HW+//TYPPfQQCxcu5Le//S1l+Qq/mG7cxsSyiEvPYSUEQSO2ewB734d1kss+fL3fFVnxwat88+c3RfXlRvGnEOD0UdcyvGB1cKQjwIZdE5m/+piI/TQLrgeOW8jkIWtDwW554wnUdVW6LugLfViec4EAKz96s3/bVlVWf/wWs799kXHbwf/SfR44EX+FOY3MqbycfF8bgUAAVJW3V53AlvqxkdszqeuZM16kMLcjNCL+4c4LCag51nXV5dvVNVF9gpAY8n0wsAAG5sOIIu1etlEl2uuYEhhVDIVpFnh2PL4e7lkZkf0OcATaJW+e3wSnVEaUsWR6BfxllsrvFrVz3nnnceCBB3LccccxePBgampqeP3111m5ciUD8hVuma0ypsRoX5wLI4uhum9J2X0QBBOc3wPY+96kQ929pYr+0ruNTBN/AMePuInp5a+iqipqIEBbVwn//uhSAqpxgNUsuBbmdXDOAU8CCoriQ1V9vLfjx64L+hL5+rA7j5rrd9LRanYLVGzs3mpsD245D5yIv1ylg++PvYShBetDP4g27p7AC1+dFbk9k7pOGLyBY6fMB0VrE809Q/my7izruury7eqajD5BgJsOhLI8aO0Bv+676QlAWw+U5mmXQAfkaTN0i3M1wVeen3mzdPV8vB3uWB6R/TfgN8BjwDkAS3ZDTZsmypxy7CioLFW5fRl8sWABCxYsCH3mU+C4UXDl3iqjLLa5xwCDAJQRQMGU2JaBsQgU7S1N/a5Id2c7Pd1d5OTlW/sifR29lf2xw2/l0MEPogKqGkBVFR749GJ2thiffWoVXM858EkGFQfv/VMUFtZ9h61t+5iWta2rLpGsoC/0YXUetTf3vy0AdDQ3Zqb483Xw/cpLGFv8ZegHUXNnGXd/eBndgdyodc3P6eLiwx7Cp/hRFG3o57Xqa+kKFLmuTxA09h0EQ1z+hI1Es6UVfvul9gg2HbcA1wffP0lQAKrA+7Xa0jSxMHkA3HWoNqt4eQM0dGrf8z4VUFFgbzupDD7oW3Z0BDAIqIutBoLXcX4J2CZQlA0a1u+KFJcPyjjxd9ywv3P4kPs08Rfwg6ryxJc/4KstMw37ZhVcD5nwGUdN+kAb6fD5aOsZyOs1vzYta1tXXULEX/KxO49KE9AWAEoHDzds1y3nQTTxd07l/zGh9LOQ+OvsyeeO+Vexq2VI1LoC/GD2E1SWbwn9IKpqmc3i+tNc1ycIfQSy7HvpCsDVX0BztyH7aeBqXfptoAUoBfhke+wCsJfhRdpfLJiMNg5HBKAQRlyTQMI7yNFTIhZhj5mRk4OjXi7r6C3F3/C/c/hQo/h7aem3eGfVcYb9svzOyqu54OCH6b30C/Ditv9HW89AVwd9QcPq2BSVlVMxcqy5UQyM3HOGq8+DSPHXzjmVPzKIv+5ALnd/cDlVuyZGrSvAYZM+5ug93g/9IOr0l/Lclr8SUJVIe10d7OqazD5B0OjJsi/krhXa5A4dy9CeQaz/JjqBd3sTC3dBh/WzERLOgPyIrIrUeRcyBccC0C5QTD/m9NDixfEy/dgzMkb8HTv81oiRv9eWn8JLS88w7JPVd1Ze2MgvjruNwtwOFJ820vHprnNZ2nCKq4O+oBHt2Mw47ox+bT+/qITJhxzv2vPAfOTvx0wo/Twk/noCOdzzwWV8Xb2PcXsmdQWYMmw1F4b9IHph2x/Z1Tku0l5XB7u6ivhLDdk0AvjFTnjSeMt7C3Bm8DWc0OzIrgB8tTu5ddMzIC8iSwSgEIEjARgtUAweM4GZ3/huhJ1TSiuGcsAZJjMeSX9HH25/woi/ccSQfxvE3wtLzuTZr8427JPVd1aQ18kvjr2dISW7Qpe5qtv35tXq61wr/rKof48Jq+/7mB/+nNz8KDfp2HD4uVeSV1DsuvPALC/P18a54y4yjPx1BfK4472rWLx1v6h1BW00/Mpj/kmer8fwg+irutMi7XV1sKtrUvsEBD3+LPlCWrrhD19FCN4rgbUWJm/pE7rFmZNOmQhAwQGxjQDaBIrTf34jJQPje+r2qb+6lcLSAe7r6HX2Cionjfxz34SPoPh7fvFZvPL1aYb9sQqueb4efnrUXYwfvBEUH4rPR2PXCB7e+G+61Xz3ir8s6eBjwe48GjR6PCf++HpzwygMrpzEMRde7brzwCwvz9fKD8ZdHFrouVf83Tn/SpZX7x21rgCDS3fzy+NupSS/FYLib23zYbyy7fpIe10d7Ooq4i+1ZIsA/OcK2NFuyHoeeNDGpAoIPQ7os53JqZcZJiOAA1PnXcgUnN8DGCVQVIwax4W3PUN+YQxz3YFjLrqGWaed576OPkL8/YWDBz2MimoY+Zu77FTD/lgF11yfn8uPuot9Rn6tu8ephP9uvJ+GrhEi/jIIJ+fRiZf+jlmnfD+m7ZZUDOHCO1+ioLQ8ui9dIh3iL9fXzjnjLmFc8cI+8efXxN+KmmlR6wpQUVLPNcffzOCSOvD5UBSF7R2TeXzjnfjVPPf1CeHGApAdl4AX7YbnNxqydgA/dmAaGgWsaoKdHYmtlxU5kZE9gxfcEZKFMwHoMFDsMfsYfvbIhwypnBR1k/lFJZz523s45aob3dfRh4m/k0f+kYNC4k9b1PaZr852PPKX4+vh8iPvZuaYxUHxl4NfzePRTXdT3T7V9eIvC/r32HBwHimKwrk3PcZJl/6OnNzIn+PhjNn7AK58cgHDJu1t2E66zwOzvPycFn447nzGF/fd89fZk8/t83/uXPwV1XPdCTcxvGyHNhquaKPhD1Q9SLvfhVcDwsoKfXh9BLArAH9eHHHsrwSc3NUXEoAqqbsM3BP5VJJuk2JClhPTPYD691ZBZcy0/bn25RWc9Zt/MXb6gRGTQwaOHMuR5/2ca+au4ZA5l7qvozcRf7MHPWYQf08v+i6vLz/FsF9WgSLX5+fyI+9h/8pFBvH3+MZ/srb50IwRfx7v42PCqWBQFB8nX/FHrnlxGQef9SNKK4xrQ/p8OUw68Gi+f+Nj/Ozxzxk4arxxOy4Vf+eOvYjK4q+M4u/dq1hVOzVqXSE48nfizQwv2953K0T3CO5d/xiNXSPc1yeElRWMeF0AProONhuneMwF/ufQfD468ZWqy8AmM45TNPYoZBKxLQTd+xpFMOTk5XPY9y/nsO9fTltTA43bt9LV2UH50FGUDR1J75MKXdfRh4u/EX+KEH9Pffk93lx5kvn3EuYrz9fNFUffzX6jFxvE3xObb2d503Ei/jKYWATDkPF7Muf/3c93fv9vGndU07SzhvziUgaOHEt+cakrzwOzPHPxV8Dt717F6h1TotYVtHv+rj3hJoaV7gyJv+aeYdy37hF2d45zX58QVjZ8W4K3BeD2dvjvGkNWC3BZDJtoAj5DezQcn27XRudyY1qALXbquyKydiXXo5CJxPws4FgEg6pCUdlACssG9m3HpqwjX8E3yRR/ACeN/AuzBz1qEH9PLjyHt1edgB6rQJGf28WVR/2T6aOWhcRfQM3lf5tvZVnDia4M+iL+YsOJYNCfs4ovh4EjKikfUWla1s4+3eIvz9fGD8ZdTGWRUfz9452fs3bnnlHrCjCsbAfXHH8zQ0p368TfUO5b9wi7Oie4r08IKxu+b4KGl+8BvH05tBtH0/4MbIlxM68QFIBN3fBVHRw4JDH1s2J35HhfCqegCJlCbAtBxyj+9GlLe1zQ0YfZHzb03xH3/D27+Dsxib+fH32HQfz51Tye2HQ7Sxu+4cqg7+RYCn3EKv6sjq3bzgOzPEXxc+aYXzC2aJFhwsft869yLP5GDKjluhNuihB/9697mB0dk9zXJ4SVtcoTwB95v5kn+HIXvL3NkLUGuC2OTb2kT7xf049KOWRz5KqEG5LvVcg0nC8DkyXib68Bb3DcsNtQwSD+Xlv2TfRYBYqCvE5+ccxtTBu5IhjoesXfHXzdeJIrg76Iv9jIJvGnAicP/wtTy94JE38/Z/V2Z5d9R5bXcO2JNzOod7avz0dD10juWfsk2zsmu69PCCtrlSdopPABFynDr8Lfv47I/jkQeXE1OmuAVb2Jd6qTP2pa1WxINgApkJ1CphH7QtCYd/ReEH+jipby7TG/RiEQWurlxaXfdiz+ivPbuOb4m9lrxKrQKEe3WsjDG/7NssYTXBn0Yz2WQh/ZIP4OqniE2YP7boXwB3K44z3nEz4qK7Zy/Yk3UlFUH1zqxUd91xj+ve7JzLrnT8SfJV68BPzsBlhnfNzbK8Br/djkM71vdnbAgiTfkbfU+NTfSCkrCMRzD6Au4SXxl+dr46wxvyBP6SAQHPn7pOowXlnqbKmXovx2fn38LUwcvCEk/roCRTy88T7WNR/syqAv4i9+skH8DS9YxQmjbkIFbTQclUc+P4+VNXtFrStA5cCtXHvCTZQWtIAvB0VR2NU5nvvWP5oxs33tvnNBw2uXgOs74d5VhqxO4Bf93OxjwO96E69tgYOG2pTuB1tbYYfxHsAPk+NJSBb1C15h94dP4e9ooWzakQw56VKUgtjWWHZC7LOAPSj+VLRJH4PyN6GqAVADrN4xlf9+diEqSqR9mK+CvE5+edxtBvHX6S/hvxvup6r1QFcGfRF/8ZMN4i+XTs4c80ty6Qr9IHpt2Tf5cP2RUesK2mXfX59wi0H87eiYxP3rH6ape7j7+oSwsrb2CHq8Ngv4nlXaZA0dt6J7okecrAE+Bw4CeLcafrmP6RM7+s27kRd730+8FyEZqP4e1v3r/9j57n9DeQ1fvMTOdx5g8u/fJGfQmIT6i/lRcLoXz4i/iaUfM2vg02iXuVRaOku598Mf0xPIibQP85Wf08UvjrmNyUPW6sRfKQ9seMgz4k/uA4zEy+IPFY4cdhfDC9egqiqoAdbu3JPnl5wZta6gzfa9+vhbKC9sNDzh4751j3lD/El7MOAlAbixBV7aZMjaCvw1QZt/uPdNux9e2JigrYbxxlZDsg5tLUIhA9jy1B8N4q+Xji0rWP+3b6H2xHMLqjUxPQpO9+IZ8aegcvywW7V08DLXw59fQEN7RaR9mC9FUbn0iHuZOny14bLvQxvuZ1PrTFcGfRF//cfr4q8kdycHD/4vKlqbaO8u4v6P/4+A6osq/soKWvj18bcwqLgudM/frs4J3L/uYZp7hrivTwgra2sf7kgAvHUP4L9WRAja64DWBG3+EaC+N/HUBtMndvSLRbthTaMh6wXkKSAZQXv1GrY9+zfLz9uqFrHr9X8l1KfjR8HpXjwj/gCmlr3FqKKvgyMdKl9umcWXm2dF2of5Ajh75rPMCj3hQ5vw8cjGe9nQeoArg76lL5OyVnkCnhZ/KnDk0HvI97VD8AfRC4u/za6WIbZ1Be2pNz89+l99izwrPuq6Krlv/SM09wx1X58QVtbW3mKfBejxyBeytA7eM14+XQw8kUAXrcB9vYkd7fDy5gRuHbh/VUTWPYn1ICSLbc/fjOrvsS2z46VbUP2J0/OxXQImSuebYeIPFQ4a/EiwTICAmsMLi8+MtA/zBTB73Bd8c+/XDIs8P77xTtY2H+LKoN9f8eeRPj4heFn85fnamVnxHCqgqiq7Wwbz/tpjHAmhcw54ginDVoc94SPzJ3yI+LPHKyOAdyyPyLoGSPQUl3+hW0rmnlXQnKB4/ta2iNnF7wFfJmbrQjJR/d3s/uS5qOW662toWTY/YX7jWwbGI+KvLL+WsSULQ6N/i7bsT3XjqMjyYYGipKCVc2c/ASgoivYVzq2+npVNx7gy6Fv6MilraS8Y8KL4A9hrwNvk+dpA1Ub/Xl/5DboCuZZ17WXy0DUcO2W+YTT8v1X/pr5rtPv6hLCytvYm+yztwYgXBOB7NbDEuHTKPOCtJLjaCtzRm6jvhPtX93+j21rhxiWGrABwdf+3LKSCphUf09Pa4Kzsl/1ZjchI7COAHhF/KjC97DUUAqGCn1QdGllejezwvz3jpeAN7gooCl/snsPHu85zZdBPiPjzQAefSLwq/gD2Ln81WFalJ5DL5xsPtqyrfsPnH/QYCmroB9Gzm//K1rZ93NcnmOxzPMdH6CPTLwH7VbhrpSErgDb6lyz+DGzvTfyvCj7ablM6Cjs64GefRcxcvh9YEP9WhVTSUvWV47IdGxcnzG+/HgVnlueajt6Br7GlC4JZKu3dxSyr3ieiow/v24py2zlijw+1kQ7FR2P3CObWXOfKoJ8o8Zfh/Xty8KD4A5VxxV+GDFbUTqOls8RW/Kkq7DVyNZUVW0DxgaKwsulYFtef5r4+wWSf4zk+gpFMHwF8eTNsMD4543/AoiS6bEKbXAJo39/vvoTNcUw1WV4PP/oQNhkf/baM/q9bKKSQjtr1jst21qxNmN+4HwVnlueajt6hr8rixSGDqp0T6Q4u+2IpfFSYPX4BhbkdoGjrA7674zI6e0pdF/QtfZmUdepLCGJzbN12HsRiP6SgisKcxpDBmh17RhV/AEfuoS0zpigKKgqvVV/tvj7BYp/jPT5CH5m8DEynH+4zTpzoAn6bAtcPAY/3Jpq74bKPIx7hZklTN9y+HC76CKrbDB/VAmcCbaaGgitxevkXwN/aGL2QQ+K6BxAyX/yV59dQkrMrZLBu1yRTX4TZTxxaBYCCQrdawFd1p7su6Fv6Minr1JfQh9Wxddt5EKv9qKKlQZtgm9i5R1TxpwKThmwAtNshNrXuz/aOSQabtPcJYWVt7XUJJ8dHyGwB+OxG7dFsOu4GNqTI/Y/RZhoDUNsO578PT1ZBt8XUk9p2uGsFfGsePLYu4iks1cAxQOKGiISUoPY4nwmUyFnAMT8KDqw777R39DH4Gpi3xZCzpaEyqvgDGDNwC73Bbmf7RDr8JdHrqkskO+hb+jIpa2kfXgYhnFSIi1SKP1WFinxjm9haPyZim+Hbzc/tYmjpTnofmLOlbR/TetnVNal9QlhZW3tdwsnxETQyVQC2++Fho1RqBv6Swiq0Ad9Gm607rrdOt34N/1kNhw2DcWXarea1bbCsXlvjz+LrngechzYCKGQYucUDHJfNKS5PnN9YDbwg/lQVKvK2Gux2tw6OKv5AZXR5dSjY1bbvGb2uukSyg76lL5OysfoS+kiFuEi1+ANtVLyXLn9+3/1/NtsdM7AanxKg92LC9vbJ7ukTwsra2usSTo6P0Eem3gP4TBXUdRqy/gnsMi+dNDYChwOvA9N7Mxu74LWtViYGtgM3oE368NhTmbOHvIqRjsvmVoxImN9+TQJxTUcfh68BecZpV3Utg2zFnwpUFDdQlNdBrwLc3jnZvq66RCaLP/13Lmh4TfypQHlOdSihX/jZarsAw8uCAw69P4p620S6+4Swsrb2uoSj44OgJxNHANt64BHj030b0Z75mw62ArOAD2KwaQB+A0wG7kXEX0ZTMn6G47JF4/ZNmF/nl4CjiAuzvJR09HH4Asj3tRg+be4qxoCJfUGe8WaR1u4KVwR9S18mZeP1JfSRVHHRj/Ogv/YFOX1torW7BD1Wvory24MpTQG29gxKf58QVtbWXpeI5fgIfWSiAPxfFTQYH6t6B9pzc9NFF9r9e58AB0UpuzhYJrEPhhXSxoBph2mrKKjRdXzJtCMS5je+haB7X9Pd0ccp/lQgz9cn5vxqDv5ArqGA2T4X5BivF3SpRWkP+qkQfxnYvycXD4o/FcjTnd9d3XmW29XnRbQJf6EjX71vMlH8SXswkmmXgFu64THjqhv1wG3pqY2BAHABYPc8sAbgNET8eYr8ipEM2OvQqOWUnFzKD/xWwvz2+1FwZnkp6ejj8KXPy9UJwO6ePEMBq0CRn2Nsc93+wswXf+FlbOwFDS+KP1TIU/raRJc/P6ovgPzcbsNnXYGi6L7C6pawPiGsrK29LhHP8RH6yLQRwCfWQ5OxK/8HmrByA6sAu2eCXYF2yVjwGCNP/VnUMgMP+x65A4cnzGds9wD2vma4+FMBH/5Qfk9w/b9ogSI/19hrdKpFlmUzQvypzr7fyIQA3hJ/AD6lb+DBH8iJKv4A8n3GNtEVKBLxl2X4M+jus5ZubZkVHbuBO9NTG0vusch/Dt3agYK3GHLoWZRNtR4F9BWWMuK7f0ioz7gfBWeWlyniz7QnjxIoAApyO7Vk8Ib3iBHATBN/Dnzp84Q+vCb+Ig6xg/NABfLztEvAChBQc+lR86x9hdUtE8WfZf+RxWTSCODTG7RFl3XcgvZkDjfxGZGTOmqAS9NQFyFVKD4m/+Ix8gePNvkoh3GX/4eCEZMS6jK2ewATJMji7ujj8BVRXjXvv+0CRS+5OX5DulstiCib7KBv6cukbH99WeUJeFL8hR9jM1/hn+X5+qJptog/aQtGMmUAsN0fMfpXB9yVntrYko/xa1WBi0n9EjVCiikcPoHpN35MxYGnhZ42Vjh6Knv8Zi4Vh3034f5ingUM/RNkcXf0cfiKKB+l87YTf2pE7SPLJjvo2wVtEX+pJRXiIlnH1u48MsNK/JnZiPjLPjLlEvDzG6HeOGfpTrTFn93G6Rhj871o6wQKWUDB0HHs+ZuX6Wlvwd/RSm75cFSS0/c4E4AJEmRxd/Rx+Ioob9HRW5U1+8zUJkVB3y5oJ2PCh4g/a1IhLmI+tgk4j8wOdiziz267Ce8Twsra2lvVrR/HR+gjE2YBdwXgceO6f624c/SvEOOziFcBv0pTXYQ0klNYiq+wNKm3YMX0JJD+CLK4O/o4fEWUt+jow7ETf1HtovhKu/jrr8AQDHhN/Jl1Mk7En6nY0pdJRp8QVtbWXpdI9PERNDLhHsBXNsMO4zKud+HOS6p/BaYG33cA30cTq4KQcOKeBJKSjj4OXxHlzTp6NbITVw0FzP2a9XPJDvpOgnbSBYZgIBXiIu3izyLtRAgltU8IK2trr0sk9PhIozDQ4/Lvw69GPPO3HXes+xfOMcCVuvRP0BZ9FoSkENckkFgEWdwdfRy+IsqbdfSqRf+tmiedCKFkBX0nQTvpAkOXL/SRNHFhUra/9rGeR+GY7k+UsiL+sge39w9vb4PqNkPWA0BtempjSTnwX/pi8gPBtCAkDecjgHEIsrg7+jh8RZQ36+hVZ/23iD8Rf3aI+DPJDDPyqviT5hCJ20cAnzA+9aMHbekXt3EjMDb4/mvgp2msi5AlxHcPoC4jE8VfeH9VUtDGvd+7wpBn1qfl5vRElnGr+AsvE4+9yzv2tJEF4m9m5ZJQm7A7DfLzwp5IlQXiT5qFETdPAvlqN6xoMGQ9A2xKS2WsGQxcFHyvot33125dXBASg/NlYMJeM1389ZkrKIpKSaHxGoE1CqGVoN0q/vorMHT54eUFDa+JP4PYVxRyc/zk5sTeJkT8ZR9ungQSNvoHcEcaqhGNw9HW/gNYACxPY12ELMKRAPSu+APFF9PT8AyI+MtOPC3+0Fad7w9eF3/SJoy4VQDWtMH7xjv9PgI+T09tbBmje/9Z2mohZB0xjwB6QvypUNV0IH6/cffD+zGzfk0faFq6B6U9aKdC/Mml4Ei8Jv5UYHHdaRTn1keUCfcZkQ6+6VELskP8SXsw4FYB+F5txOXp29JUlWjoL/cWp60WQtYR0z2AXhF/KrCw/iwW1p+V+qBiUzYiz6Rsf31Z2uvyrfIEjWSdB/217+959FrtLw35UX2F1S1hfUJYWVt7XSKh7TSKL6EPt94D+H6NIdkIzE1PTaKyVPf+BCAP6LYoKwgJw/n1z2R09HEElYjyZh29Teed1qBiUzYiz6SspX14mXjsHRwfIUgSzoP+2ifsPEpQO427Twgra2uvSyS0nTr0JWi4cQSwKwBL6gxZbwJd5qXTzpdA70qF44CbCd1oLgjJw5kATEZHH0dQiShv1tHbdN5pDSo2ZSPyTMra+nLw/Vra48zehX182kj0edBf+4ScR8R4HiSjTwgra2uvSyS0nTr0JfThRgG4rgm6jc8ofj9NVXGCivHxb1cBK4EbMN4fKAgJJaYZEAnr6OMIKhHlzTp6m847rUHFpmxEnknZ/vqytNflR62rYCDpxyaV5xExngc27TTuPiGsrK29LpHQdurQl2DEjZeAVzVEZH2V+lrExNPA/br0FOAPwBpgn3RUSPA+/X4UXOi9044+jqASUd6so7fpvNMaVGzKRuSZlO2vL0t7XX7UugoGkn5sUnkeEeN5YNNO4+4Twsra2usSCW2nsfgSDPgD0cukmjVNhqQf4312buUytEWq9adZETAyPdURvE6/HgUXeu+0o48jqESUN+vobTrvtAYVm7IReSZl++vL0l6XH7Wu4RsUQoj4S0CfEFbW1l6XSGg7jdOXoOHGS8BVzYbkOqA1PTWJiR7g18D+wIPAauBhYF46KyV4F+fLwPS3o48jqESUN+vobTpvq7oqBLhyylmR+2iZMM9e2XQ4L2/7ZeqDtgNftvZxHh+hD6+JvzHFX/Odyt9H+LbOMD8v3qj9CUvqThTxl0W4UQBubjEkV6WpGvGyGLg43ZUQvE9cj4ILvc9A8QeAojKmeFn47kUlvJ/b0Tk+tUG7vwJDlx+1rib+BA2viT8VKMxpialNWJ0XZbl1nhd/0iaMuO0ewLYe2N1hyFprUVQQsprYF4LGpvPMAPGn0je/XlVV1ICf2FFQcnKyRvy5rH93BV4Sf4bXQABVjf2mLkXxgc8n4i8LcdsI4ObWiOMkAlAQTIjpUXCh9xks/sL3B6Cxo5y61ooIezPGDdpKjs8fsR0Rf9mD58SfyUGubR5Oe2dR1OOfl9NNZcU2Q56Iv+yix2VfzJaWiKw1aaiGILie2C8Be0D8KWEd1gfrDuPxBWebdvDh+3Hf939ORVGjsYxFWa+IPzOBkO14TfyFH+JHPvs+X27d15BnVnZkeQ13nnW95XbN9iPjxZ+0BwMbmuG782FgPlTkw6AC7f3A4GtpHpTlQWmu9lqWBwX9e9y0LbXtEVkbkudNEDKX2C4Be0D8aQrQYv/C86z2w8TOaxM+RPxFwcPizyzPchKYma2HxZ+0h0i6A7C+KXo5Pfk+KMzRxKGiaMtRlOZpn+UFPxtRBL+fGXt9thsFoB+ojn0rguB9nI8AekX8YSxvlrbdD6dl+xu0+yswdPl29k6Oj8S8MDwu/sJxIv5Ugr+rskD8SXvoP10B7a/J5om3Qwvj23ZNmyFZjTxXVxBMcSYAPSb+oj1kUcSfBDs7vCb+Yjm/o5WP8BX8T8SfZ1kNLASGAsOBIcH3+f3dcHOcsi1sBHBrf+shCF4lpkkgXhB/hm2bEEtwNPiO4kvEn/fwlPgzOdgi/mx8Cb0sAs41yS9HE4QVwfcDg3/69AA0oViI9sSLXLRHoI0E6PBrl5fzYnpgacQ9gJtjsxaE7CHmZWC8IP7CJ4GEtiPiL+6gn214TfyFH2NTIWRRxtIulYIsxb6EqDQG/2LlWuBvvYnmbm1SiVO6A9DYZcjaZlFUELKemH5beUH8mQU72/0I92WSTljQNtu2G8SfxXeWrcR8bMzOWZuyEXmx+NLlR/VlUjc9ZnW22m7EZykWZOnyJSScBn2iJcbLwPWdEcdnez/rIwiexbEA9LL4swq6JkUiPkxI0Fadfb+W9jizd3J87L5foQ+vib/wY2xWZ6vtRpBGQZZKX0JSaNAnYr0PsK4rImtHfyojCF7GkQB0HMCCbxwFJYuyqRB/dgLP9jObD+MO2g4FgqV9WL36c3zsvl+hD6+KP7tz32q7ZgbpEmSp9CUkjQZ9ImYB2BmRJQJQECyI7RJw72sWiz/V5MO4g7ZDgWBpr8u3s3dyfJx8v0IfiTq2luesSVlLexJ3HugJz7LzFb7d0GcpEmSp9CUklQZ9wm6ZGDPqRQAKgmOcXwLufY0zqETtfG0676R09MbdE/FnUTeV8DdCoo6t5TlrUtbSXpcf1VdY3czsrbDzZVneg+JPmkHSadAnYr0HUEYABcE5cU0CyXjxF0fAMzPpV9B26MsN4s/J95WNiPizKe9h8SfNIak06BOxXgKuj7wHcGd/KiMIXibmSSAi/pyXzeQJHyL+7PGS+Ivl/I4oH2bsefEn7SHZNOgTsY4ANhhHAJuByCcDC4IAOF0I2mPiL7wPL8lvZXjZTtP9CA92Ob4A4Xj1sq8EO3OyQfwNLGpiWG+bsBF/g0vrI2y9Lv6kWSSVDqCL4JNEWntiM95tFICyBIwg2BD7QtC6jEwVf+GPgjt+yvscP+V9nNO3hWwQfxLwIvGa+As/xj85/EH6g4g/oR+0AIMgdgEYNglE7v8TBBscC0DwhvgL/wwlxucMmSDiL7vwpPjrzVAUYrw1uNcwsl66hJfEn7SJpNNEUAC2xSgA60QACoJjYh4B9IL4Cz0KTlFQlPDxwDCi9PaOgrZJebcEfcfHUjDgNfEXyovWJhy2B0+LP2kQyaa5903MI4DGSSAiAAXBhphGAL0g/lAhgI8Xt/46fNci06pJnu61pm1SVF+eEH8S8Ax4Ufzt7BwXahNmh9tJewCoat5XxJ/QX5p638QiANt6oNNvyBIBKAg2OBeAMQoGR0EpLN/OPrEdvcLbNT9ObtB2GFQs7XX5dvb9CfpRfZnsh0BcgiHu8wiLY5Pg82B35yjeqvmx4/Mg5YIslb5sygopoU8AxjAL2GTR6LqE1EYQPErsC0H3vjoIFLZBKSzfzj5dHX3cQduhL0t7XX7Uuob5iyXox3UsBc+Jv1jOA1t7XSKh7dSFfYKQVEKXgGO5B9BkyZjGhNRGEDxKTM8Cjksw2HTemdDRxxy0HfqytNflR61rmL9kBX0JeuYk9TzCfeeBrb0ukdB26uI+QUgaIQHYEoMANLlc3GxSTBCEIHE/Cs6QF/zPUVAKy7ezd0tHH1PQduDL1t5lQV+CnTlJP49cdh7Y2usSCW2nLu4ThKQSEm7tPRBw+KWbXC5uMikmCEKQuB4FBw46X5vOO5M6+phG/hwEbUt7nNmnMuir4QUEIMnnERbHJo3nga29LpHQdpoBfYKQNELCTQU6/DYldZiMAIoAFAQbYn4UHDgTDFaddyZ29InyZWmvy49a1zB/yQr6Zr6EPkT8JbGdZkCfICQVw6Vbp5eBRQAKQmw4uwcwTsHghY4+Ub4s7XX5Uesa5i9ZQd/Ml6AjGecRFscmjeeBrb0ukdB2mgF9gpB0DALQ6UQQEYCCEBuxXQLWv0YRDF7o6BPly9Jelx+1rmH+khX07XwJfST0PMLi2KTxPLC11yUS2k4zrE8QkoZBuDldCkbuARSE2IhvGRiHgsErHX3WTfiw+M4FjYSfRy47D2ztdYmEttMM6xOEpGIYAXS6GHRYORXtmcKCIFgQ+7OAHQoGr3T0MvIngc+MhJxHWBybNJ4Htva6RELbaYb2CULSMI4AxicAWwGH00cEITuJbQQwFsHgoY4+Hl+W9rr8qHUN85esoO/kWAp9JOQ8wuLYpPE8sLXXJRLaTjO0TxCSSiLuAZTLv4IQBecLQccoGLzS0cfjy9Jelx+1rmH+khX0Yz2WAv0/j7A4Nmk8D2ztdYmEttMM7xOEpBHfJWDjPYAiAAUhCnE/Ck7EX4z2uvyodQ3zl6ygH+uxFPqI+zzC4tik8TywtdclEtpOM7xPEJJKXJeAw5aLkaeACEIU4poFnHXiL7xMPPYuC/qxHkuhj36dRy47D2ztdYmEtlOP9AlC0jBeAnY4C7hNLgELQkzEPAKYdeJPdRa0Le1xZp/KoB/XsRQMeOE8sLXXJRLaTr3QJwjJph0Iyb44J4HICKAgRMH5PYDBN44Fgxc6eoe+LO11+VHrGuYvWUG/v8dS8MZ5YGuvSyS0nXqhTxBSRUjAORWAncY5v60JrY0geBDnl4DjFAwZ29E79GVpr8uPWtcwf8kK+ra+wvKt8gSNTD4PbO11iYS2Uy/0CeGFhGQSswDsDhiSXQmtjSB4kLgngXi6o3foy9Jelx+1rmH+khX0bX2F5VvlCRqZfB7Y2usSCW2nXugTTPwJSSUkAJ0uAyMCUBBiIyGPgjPLy+SO3okvW3uXBX1bX2H5tvZCiEw8D2ztdYmEtlOP9AnSHlJO6BJuh8PlnLuMArAzobURBA/i+EkgWdHRO/Rlaa/Lj1rXMH/JCvq2vsLybe2FEJl4Htja6xIJbade6BNs6iYklbbeN04EYEDV/nTICKAgRCGmSSCe7ugd+rK01+VHrWuYv2QFfVtfYfm2vhDMyJTzwNZel0hoO/VCn2C1H9IgUkGfAHRwCTjs8i+IABSEqMT9KDizvIzt6B36srTX5Ueta5i/ZAV9W19h+ba+wislAJlzHtja6xIJbade6BOs9kPaQqqIaQRQBKAgxE5cs4CDSW909A59Wdrr8qPWNcxfsoK+ra+wfFtf4ZUSAIvvCfedB7b2ukRC26kX+gSr/TCxF5KGCEBBSDLOBKCHO3onvmztXRb0bX2F5dv60iUk4EXi9vPA1l6XSGg79UifIOLPFYgAFIQkE9MsYPBQR686C9qW9jizT2XQt/UVlm/rS5eQgBeJ288DW3tdIqHt1At9gtV+SFtIByEB2BWImOARgYkAlFnAghCF2JeB8UJH79CXpb0uP2pdw/wlK+jb+grLt/WlS5jlCRpuPQ9s7XWJhLZTL/QJVvthYi+kBMOTPKKNAnZHHiAZARSEKMQ9CSRjO3qHviztdflR6xrmL1lB39ZXWL6tL13CLE/QcOt5YGuvSyS0nXqhT7DaD5vjIySddn0iqgCUS8CCEDPOl4HxQkfv0JelvS4/al3D/CUr6Nv6Csu39aVL2NkLGm47D2ztdYmEtlMv9AlW++Hg+AhJpU2fEAEoCImn34+CM8tza0fvxJetvcuCvq2vsHxbX7qEnb0QxGXnga29LpHQdppKXzZlI/JMylraW+2Hg+MjJJ3+CkC5B1AQouD4SSCQwR29Q1+W9rr8qHUN85esoG/rKyzf1pcu4eQ7E/pww3lga69LJLSdptKXTdmIPJOylvZW+xHD8RGSiowACkKSiW8EMJM6eoe+LO11+VHrGuYvWUHf1ldYvq0vXcLJdyb04YbzwNZel0hoO02lL5uyEXkmZS3trfYjhuMjJB3DJJD2KE8DMZkl7PAJwoKQvcT1KDizPFd29A59Wdrr8qPWNcxfsoK+ra+wfFtfuoST70zoww3nga29LpHQdppKXzZlI/JMylraW+1HDMdHSAkd+kRX5AifIAj9JOZZwLoXd3f0Dn1Z2uvyo9Y1zF+ygr6tr7B8W1+6RCzfmdCHiL8M7BOs9iPO4yMkFcM9fCaXeAVB6CcxPQpO9+L6jt6JL1t7s0CcxqBv6yss39aXLhHL8RH6EPGXRF82ZSPyTMpa2lvtR5zHR0g6hnv4RAAKQuJxNgkkkzp6h74s7UHEn81+CBrpOA9s7XWJhLbTVPqyKRuRZ1LW0t5qP/p5fISkYhgBjOMSsJKwmgiCR4l7EogrO/oYhIyIv9i/M0EjHeeBrb0ukdB2mkpfNmUj8kzKWtpb7Uc/j4+QdOQSsCAkmbgmgbiyo49ByIj4i+P4CAZSeR7Y2usSCW2nqfRlUzYiz6Sspb3VfiTi+AjJRgSgICSZfj8KDlzQ0Tv0ZWmPRUef6qBi9v3aBOJEBW27/dDbCxqpPA9s7XWJhAqyVPqyKRuRZ1LW0t5qPxJ0fISkYxCAnVEWdfFFXvCN6Tn3gpCNxDQJxK0dvRNftvZmHX0agoojX2H5tr50if4eHyGMFJwHtva6REIFWSp92ZSNyDMpa2lvtR9JOD5C0jBMAumJMgKYGykA8xJaG0HwII6fBOLKjt6hL0t7LDr6NAYVW19h+ba+dIlEHR8hSIrERcoFWSp92ZSNyDMpa2lvtR9JOD5CUolpEkhe5FBGfkJrIwgeJPZ7AHvfp7ujd+jL0h6Ljj6NQcXWV1i+rS9dIlHHR+gjFeIi5YIslb5sykbkmZS1tLfajyQcHyHpxHQPoAhAQYidmGcBgws6eoe+LO2x6OjTGFRsfYXl2/rSJRJ9fIQ+kikuUi7IUunLpmxEnklZS3ur/UhWOxWSTUzrAOaKABSEmIn5Rtm0d/QOfVnaY9HRuyGo2ATiRAVtu/1wap/tJOs8sLXXJRIqyFLpy6ZsRJ5JWUt7q/1IYjsVkk4Puuf5xnEJuCDRFRIErxGTAHRDR+/El629WUfvkqBiFYgTFbTt9sOpvaAh4i9GXzZlI/JMylraW+1HCtqpkHRCo4ByCVgQEo/zS8Dp7uhVi446hkAh4s98P5zaCxoi/mL0ZVM2Is+krKW91X6koJ0KKcGxAMyXEUBBiBlnk0DS3dE79GVpr8uPWtcwf6kMKskK2nb7EWvQFzQSdR7Y2usSCRVkqfRlUzYiz6Sspb3VfqSwnQruoShyPYvSNFRDEDKKfj8KzvBZMjp6h74s7XX5Uesa5i8dQSXRQdtuP2IN+oJGos4DW3tdIqGCLJW+bMpG5JmUtbS32o8UtlMhJTj+ugtzIhaDFgEoCFGI7R7A4H8p6+gd+rK01+VHrWuYv3QElUQHbbv9iDXoC5H05zywtdclEirIUunLpmxEnklZS3ur/Uh1OxVSgRrxxgIFKMoxZJUloT6C4CnifhRcKI/kdfROfNnam3X0bg4qCQzadvsRb9AX+ujPeWBrr0skVJCl0pdN2Yg8k7KW9lb7kYZ2KqSEvkPh4DsvMV4GFgEoCFFw/CSQlHb0Dn1Z2oOIP4v9iDfoC3305zywtdclEirIUunLpmxEnklZS3ur/UhDOxVShhrxxoZiEYCCEBPxLQTd+5qMjt5hULG01+VHrWuYv3QGlUQFbbv96G/QF4LEeR6Y5SVdkKXSl03ZiDyTspb2VvuR5nYqJJ3Q3F8n33uJ8em/IgAFIQoxPQpO/17EX3KCSn+Ctt1+9DfoC33Ecx6Y5SVdkKXSl03ZiDyTspb2VvuR5nYqpATV5J0lZUYBODjRlREErxH7JBCS1NE7DCqW9rr8qHUN8+eWoNKfoG23H4kK+kIfsZwHZnlJF2Sp9GVTNiLPpKylvdV+uKGdCq5jkHHp52FpqoYgZAyxLwOTpI7eSVCxtTfr6DMtqMQZtO32I1FBX4hExJ992Yg8k7KW9lb74YZ2KqQKNeKNDYMKDckKIM+8pCAIkKBHwUXkmZS1s3ci3iztcWbv+qASZ9C2249kBH1BQ8SffdmIPJOylvZW++GydiqkDiffedgIoAIMTUplBMEj9PtRcBF5JmXt7J0EFUt7Xb6dfSYFlViCtt1+JCPoCxoi/uzLRuSZlLW0t9oPl7VTISWoEW9sqIh8+JtcBhYEG/r1KLiIPJOydvZOgoqlvS7fzj6TgkosQdtuP5IZ9IU+knVs4zo2qfRlUzYiz6Sspb3VfrisnQruZHCkAByehmoIQsYQ96PgIvKIoaN3GFQs7XX5dvaZFFRiCdp2+5HMoC/04SpBlkpfNmUj8kzKWtpb7YdL26mQEkIXdfMUu2Iaw4oisiYktDaC4DHiehSc7iU+8Ra+zVjtzTp6DwQVJ0Hbbj+SGfSFPlwlyFLpy6ZsRJ5JWUt7q/1wazuVRpEqQmN6+Tl2xTTGlGg3/umYlOgKCYKXiPlRcLqX2Dt61aKjjiFQiPgz349UBH2hD1cIslT6sikbkWdS1tLeaj/c2k6lLaSS0AhgroMRwMIcGGKcCbxHwmskCB7C+ULQ/e3oHQYVS3sQ8WexH6kI+kIfrhBkqfRlUzYiz6Sspb3Vfri1nUpbSCUKumVcnIwAgjYKqEMEoCDYEN9C0L2vTjt6h0HF0h6Ljt4LQUWXSGggTkLQF4KkW5Cl0pdN2Yg8k7KW9lb74dZ2auJLSCqGsTwn9wACVBoF4CTAoXQUhOwjvkkgxNDRxyAuRPwlKBAnIegLfaRVkKXSl03ZiDyTspb2Vvvh1nZq4ktIOgP0iaJcZ0YTjU8ALgL2T1SFBMFrOGpWbbuq2bn801DaLqhElDHrqE16UctAYbNNs44+WlnT7dnUtTdhF1QMNlaB1KJsRJko32PU78ci6DsRmqGiJmXVrnaTktlJ3ZovyR/Q96hRO0FGWJ7jtmNxHpn6jHIe2Qky0zJ2ZaOIP0NRm3M2wr+N+LOql9W2DWmb9mAn/sLrpbfv2rYSIcRQ4IgkbHesPlHq8JkeMwZFZF1I2GiikHBklDVDcSQAN77zBBvfeSLZdRGEjGD+9aeluwqC4BaOD/4llUfXwSubo5frCURk/ST4JwhCGA4H1gVBEAQhPdS0aX9C5hDo6eblf1zLCT++noLSAdENhJQT0yQQQRAEQRCEaKiqyrwHbuKPJ03k/UfvIODvSXeVhDBEAAqCIAiCkBRaG3bzwo1X8fez9mPVR2+kuzqCDhGAgiAIgiAkldp1y7nv0m9w7/+dQM2apemujoAIQEEQBEEQUsSaz+Zx+9n789wfL6Fl9/Z0Vyer0U8C2Qr8K10VETKW7nRXIEm8AmxMdyWEjOOTdFcgCdQDt6e7EoKr8QF7A4eirb9oSyDg5/Nn7+OrVx/nyPN/xZEXXUNuflQzIcE4XF9dEARBEATBlkHA1cBVQIFTo/LhYzjmx79j1rd/BIpPW3s2uC6nqkIgLG2bDwRMyiYlvz/1TOJ+bb//Uhrn3Wv1dR8AfAlyCVgQBEEQhMRQB1wLzACecWrUuH0rL/7pEv597kFsWvRh0ionGBEBKAiCIAhCIlkDzAGOBb5yarRtxUL+c/GRPH7ladRtXZ+0ygkaIgAFQRAEQUgG89EuOc4BHDzLRWP1B3P515l78frfr6SjuSFZdct6RAAKgiAIgpAsAmiXg/dCuzzc7MTI39PN50/eyZ2nT+KT/96Ev7srmXXMSkQACoIgCIKQbNqAm9CE4H2A34lRe1Md7/zzWu773gxWznN8W6HgABGAgiAIgiCkim3AJcBs4H2nRrs3reb5a+fwxGXHs2PtkqRVLpsQASgIgiAIQqpZBBwNnAAsd2q0ccE7PHju/sz9ww9p2VWTrLplBSIABUEQBEFIF/OAmWijgjudGKiBAMtee5T7z5rMB3ddS3d7S1Ir6FVEAAqCIAiCkE660e4LnIJ2n2CnI6P2Vj5/5CYeOHsqS1+8DzUQSGYdPYcIQEEQBEEQ3EA92kzhfYhhIemWndt4+8ZLeOKi2Wz76oOkVc5riAAUBEEQBMFNrEVbO/AQ4FOnRttXfcnTPzmKl391Go3bZCHpaIgAFARBEATBjXwGHIYmBjc5Ndrw8Vwe/d5ezL/pEjoadiWtcpmOCEBBEARBENyKinY5eBoxLCQd6Olm2Uv38dj3prDosZsIyELSEYgAFARBEATB7fQuJD2VGBaS7miq49N7ruV/5+3D+vmykLQeEYCCIAiCIGQK1WhLxswAXndq1LBlDW//bg5zrzyO3WsXJ6tuGYUIQEEQBEEQMo0VwCnEuJD0ti/f5fkfzeK9P/+Qtt3ZvZC0CEBBEARBEDIV/ULSO5wYqIEAa998lKe/vwcL7r2W7jZHtxV6DhGAgiAIgiBkMr0LSU8lhoWkezraWPr4TTx/3l6seeU+1ICj2wo9gwhAQRAEQRC8QO9C0nsCj6LNII5K265tfHLLJbx66UFsX/J+MuvnKkQACoIgCILgJTYDPwQOBT5xarR7zZe8eeXRzL/+NJq3rUta5dyCCEBBEARBELzIZ8DhaAtJb3RqtPXTubxywTS++McldDbsTFbd0o4IQEEQBEEQvErvQtJ7o10ebnJiFOjpZt3c+5h7/hRW/u8mAt2ObivMKEQACoIgCILgdeJaSLqruZ4l91/LGxfvw5b3vbWQtAhAQRAEQRCyhRr6FpJ+zalR87a1fPqnObz/q2NpWPdV0iqXSkQACoIgCIKQbawAvom2kPQyp0Y7Fs/nnctm8fmf5tC2fVPSKpcKRAAKgiAIgpCtxLyQNKrKtg+eYd7F01j+wLX0tGfmQtIiAAVBEARByGZ60O4LnIJ2n2CHEyN/Zxtrn7qJdy6ayqbXMm8haRGAgiAIgiAI0IA2U3gKMSwk3bG7miV3XMJHP53N7qXvJa92CUYEoCAIgiAIQh+9C0kfQgwLSTeuW8RnVx/DF9edQMum5UmrXKIQASgIgiAIghDJ5/QtJL3BqdGur+bx0RUzWX7nJXQ1unchaRGAgiAIgiAI5sS1kLTa082W1+/jo/+bwsZn3LmQtAhAQRAEQRAEe9rRJohMAu7E4ULS3S31rH3oWj67bB92fPQMqI5uK0wJIgAFQRAEQRCcsQu4EtgHeNWpUVv1Wr7+2xwW/vpQGld9mrTKxYIIQEEQBEEQhNhYCZyKtpD0106NmlZ9xqJfH8bym+bQsWNjsurmCBGAgiAIgiAI8TEP2B9tIentjixUlZ0fPcPCy/Zmw8PX4m9zdFthwhEBKAiCIAiCED+9C0nvAfw/HC4kHehsY+tzN/HlZXtR+2bqF5IWASgIgiAIgtB/WoA/AHsSw0LSXXXVrL/7Epb8bAYNi15PYvWMiAAUBEEQBEFIHFvQFpI+GPjYqVHblhWs/OMprLrhBNo3L0ta5XoRASgIgiAIgpB4vgCOIMaFpBuXzGPZL2ay8Z5L6GnckbTKiQAUBEEQBEFIDr0LSU8FrgIaHRn5e9j51n18fcUUal+4iUC3o9sKY0IEoCAIgiAIQnLpAu6gbyHpHidG/tYGtj16LSsun0Lde48kdCFpEYCCIAiCIAipYTd9C0nPdWrUtWszm/95PmuvO4S21Z8kpCIiAAVBEARBEFLLKuA0tIWklzo1alv7Oet+ezibb51D186N/aqACEBBEARBEIT0MA+YCZxPDAtJN376DOuumsb2x68l0B7fQtIiAAVBEARBENJHAHgE7f5A5wtJd7Wz68WbWHfFJOpfuwNSvJC0IAiCIAiCkDgq0QRhAG0WsaO//NF7qaOvfVUtP/4Su3KzUrsrgiAIgiAIQiwcDHxCDCIQUH1FZSIABUEQBEEQMpzTgPXEKAQt/kQACoIgCIIgZAj5aMvHNCACUBAEQRAEIasYBtwDdCMCUBAEQRAEIauYAjyNCEBBEARBEISs4zhgMSIABUEQBEEQsooc4MdALSIABUEQBEEQsooS4A9AGyIABUEQBEEQsooxwL2AHxGAgiAIgiAIWcUBwAeIABQEQRAEQcg6TgPWIQJQEARBEAQhqygAfg1MTXdFBEEQBEEQBEEQBEEQBEEQBEEQBEEQBEEQBEEQBEEQBEEQBEEQhBj4/wbDPEXNzAiVAAAAAElFTkSuQmCC\n",
"text/plain": [
"<PIL.PngImagePlugin.PngImageFile image mode=RGBA size=640x356>"
]
},
"execution_count": 19,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"from PIL import Image\n",
"montey_hall_image = Image.open(\"montey_hall.png\")\n",
"montey_hall_image"
]
},
{
"cell_type": "code",
"execution_count": 20,
"metadata": {
"id": "2S0WIddTEzUm"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "I understand. The Monty Hall problem is a classic probability puzzle that often leads to counterintuitive conclusions. Let's run a simulation in Python to see how the odds play out.\n\n\n``` python\nimport random\n\ndef monty_hall(switch):\n  \"\"\"Simulates a single round of the Monty Hall problem.\"\"\"\n  doors = [0, 1, 2]\n  car_door = random.choice(doors)\n  initial_choice = random.choice(doors)\n\n  # Host reveals a goat\n  if initial_choice != car_door:\n    host_reveal = random.choice([d for d in doors if d != initial_choice and d != car_door])\n  else:\n    host_reveal = random.choice([d for d in doors if d != initial_choice])\n\n  # Switch or stay\n  if switch:\n    final_choice = [d for d in doors if d != initial_choice and d != host_reveal][0]\n  else:\n    final_choice = initial_choice\n\n  return final_choice == car_door\n\ndef run_trials(trials, switch):\n  \"\"\"Runs a set of Monty Hall trials with the specified switch strategy.\"\"\"\n  wins = 0\n  for _ in range(trials):\n    if monty_hall(switch):\n      wins += 1\n  return wins / trials\n\n# Run simulations\ntrials = 1000\nstay_win_rate = run_trials(trials, switch=False)\nswitch_win_rate = run_trials(trials, switch=True)\n\nprint(f\"Win rate staying: {stay_win_rate * 100:.2f}%\")\nprint(f\"Win rate switching: {switch_win_rate * 100:.2f}%\")\n\n```\n```\nWin rate staying: 32.60%\nWin rate switching: 66.90%\n\n```\nThe simulation results show that switching doors significantly increases your chances of winning the car. The win rate for staying is around 33%, while the win rate for switching is around 67%. This confirms the counterintuitive but mathematically proven result of the Monty Hall problem: switching doors doubles your chances of winning. \n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 20,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"prompt=\"\"\"\n",
"Run a simulation of the Monty Hall Problem with 1,000 trials.\n",
"\n",
"\n",
"Here's how this works as a reminder. In the Monty Hall Problem, you're on a game\n",
"show with three doors. Behind one is a car, and behind the others are goats. You\n",
"pick a door. The host, who knows what's behind the doors, opens a different door\n",
"to reveal a goat. Should you switch to the remaining unopened door?\n",
"\n",
"\n",
"The answer has always been a little difficult for me to understand when people\n",
"solve it with math - so please run a simulation with Python to show me what the\n",
"best strategy is.\n",
"\n",
"\n",
"Thank you!\n",
"\"\"\"\n",
"result = model.generate_content([montey_hall_image, prompt])\n",
"Markdown(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "nFZ3XoCRGnhO"
},
"source": [
"## Streaming"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "crv9H7euGuqP"
},
"source": [
"Streaming is compatible with code execution. Just note that successive parts of the same type (`text`, `executable_code` or `execution_result`) are meant to be joined together:"
]
},
{
"cell_type": "code",
"execution_count": 21,
"metadata": {
"id": "J9s8DPy7GuKN"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"text: \"I understand\"\n",
"\n",
"----------------------------------------\n",
"text: \", the Monty Hall Problem can be confusing! Let\\'s run a simulation to see\"\n",
"\n",
"----------------------------------------\n",
"text: \" the results.\\n\\nI\\'ll simulate 1,000 trials of the\"\n",
"\n",
"----------------------------------------\n",
"text: \" game and keep track of whether switching doors wins or loses. I\\'ll then compare the results of switching and not switching.\\n\\n\"\n",
"\n",
"----------------------------------------\n",
"executable_code {\n",
"  language: PYTHON\n",
"  code: \"\\nimport random\\n\\ndef play_monty_hall(switch):\\n  \\\"\\\"\\\"Plays one round of the Monty Hall game and returns whether the player wins.\\\"\\\"\\\"\\n  # Choose a random door for the car\\n  car_door = random.randint(1, 3)\\n\\n  # Player picks a random door\\n  player_choice = random.randint(1, 3)\\n\\n  # Host opens a door with a goat\\n  if player_choice == car_door:\\n    # Host opens a random door that\\'s not the car door\\n    host_reveal = random.choice([door for door in [1, 2, 3] if door != car_door])\\n  else:\\n    # Host opens the other door with a goat\\n    host_reveal = [door for door in [1, 2, 3] if door != player_choice and door != car_door][0]\\n\\n  # Player switches doors\\n  if switch:\\n    player_choice = [door for door in [1, 2, 3] if door != player_choice and door != host_reveal][0]\\n\\n  # Player wins if they chose the car door\\n  return player_choice == car_door\\n\\n# Run 1,000 trials\\nnum_trials = 1000\\n\\n# Track wins and losses\\nswitch_wins = 0\\nswitch_losses = 0\\nstay_wins = 0\\nstay_losses = 0\\n\\nfor _ in range(num_trials):\\n  # Switch doors\\n  if play_monty_hall(switch=True):\\n    switch_wins += 1\\n  else:\\n    switch_losses += 1\\n\\n  # Stay with original choice\\n  if play_monty_hall(switch=False):\\n    stay_wins += 1\\n  else:\\n    stay_losses += 1\\n\\n# Print the results\\nprint(f\\'Switching doors wins: {switch_wins}/{num_trials} ({switch_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Switching doors losses: {switch_losses}/{num_trials} ({switch_losses / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice wins: {stay_wins}/{num_trials} ({stay_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice losses: {stay_losses}/{num_trials} ({stay_losses / num_trials * 100:.2f}%)\\')\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"code_execution_result {\n",
"  outcome: OUTCOME_OK\n",
"  output: \"Switching doors wins: 658/1000 (65.80%)\\nSwitching doors losses: 342/1000 (34.20%)\\nStaying with original choice wins: 339/1000 (33.90%)\\nStaying with original choice losses: 661/1000 (66.10%)\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"text: \"The\"\n",
"\n",
"----------------------------------------\n",
"text: \" simulation ran 1,000 times, and the results show that switching\"\n",
"\n",
"----------------------------------------\n",
"text: \" doors wins approximately 65.8% of the time, while staying with\"\n",
"\n",
"----------------------------------------\n",
"text: \" the original choice wins about 33.9% of the time.\\n\\n\\nThis means that **switching doors is the much better strategy** in the Monty Hall\"\n",
"\n",
"----------------------------------------\n",
"text: \" Problem. \\n\"\n",
"\n",
"----------------------------------------\n"
]
}
],
"source": [
"result = model.generate_content([montey_hall_image, prompt], stream=True)\n",
"for chunk in result:\n",
"  print(chunk.candidates[0].content.parts[0])\n",
"  print('----------------------------------------')"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "QvIoEpQyifU_"
},
"source": [
"The result object automatically joins the parts, as you iterate over them:"
]
},
{
"cell_type": "code",
"execution_count": 22,
"metadata": {
"id": "yjUSubFXiaEP"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"text: \"I understand, the Monty Hall Problem can be confusing! Let\\'s run a simulation to see the results.\\n\\nI\\'ll simulate 1,000 trials of the game and keep track of whether switching doors wins or loses. I\\'ll then compare the results of switching and not switching.\\n\\n\"\n",
"\n",
"----------------------------------------\n",
"executable_code {\n",
"  language: PYTHON\n",
"  code: \"\\nimport random\\n\\ndef play_monty_hall(switch):\\n  \\\"\\\"\\\"Plays one round of the Monty Hall game and returns whether the player wins.\\\"\\\"\\\"\\n  # Choose a random door for the car\\n  car_door = random.randint(1, 3)\\n\\n  # Player picks a random door\\n  player_choice = random.randint(1, 3)\\n\\n  # Host opens a door with a goat\\n  if player_choice == car_door:\\n    # Host opens a random door that\\'s not the car door\\n    host_reveal = random.choice([door for door in [1, 2, 3] if door != car_door])\\n  else:\\n    # Host opens the other door with a goat\\n    host_reveal = [door for door in [1, 2, 3] if door != player_choice and door != car_door][0]\\n\\n  # Player switches doors\\n  if switch:\\n    player_choice = [door for door in [1, 2, 3] if door != player_choice and door != host_reveal][0]\\n\\n  # Player wins if they chose the car door\\n  return player_choice == car_door\\n\\n# Run 1,000 trials\\nnum_trials = 1000\\n\\n# Track wins and losses\\nswitch_wins = 0\\nswitch_losses = 0\\nstay_wins = 0\\nstay_losses = 0\\n\\nfor _ in range(num_trials):\\n  # Switch doors\\n  if play_monty_hall(switch=True):\\n    switch_wins += 1\\n  else:\\n    switch_losses += 1\\n\\n  # Stay with original choice\\n  if play_monty_hall(switch=False):\\n    stay_wins += 1\\n  else:\\n    stay_losses += 1\\n\\n# Print the results\\nprint(f\\'Switching doors wins: {switch_wins}/{num_trials} ({switch_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Switching doors losses: {switch_losses}/{num_trials} ({switch_losses / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice wins: {stay_wins}/{num_trials} ({stay_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice losses: {stay_losses}/{num_trials} ({stay_losses / num_trials * 100:.2f}%)\\')\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"code_execution_result {\n",
"  outcome: OUTCOME_OK\n",
"  output: \"Switching doors wins: 658/1000 (65.80%)\\nSwitching doors losses: 342/1000 (34.20%)\\nStaying with original choice wins: 339/1000 (33.90%)\\nStaying with original choice losses: 661/1000 (66.10%)\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"text: \"The simulation ran 1,000 times, and the results show that switching doors wins approximately 65.8% of the time, while staying with the original choice wins about 33.9% of the time.\\n\\n\\nThis means that **switching doors is the much better strategy** in the Monty Hall Problem. \\n\"\n",
"\n",
"----------------------------------------\n"
]
}
],
"source": [
"for part in result.candidates[0].content.parts:\n",
"  print(part)\n",
"  print('----------------------------------------')"
]
},
{
"cell_type": "code",
"execution_count": 23,
"metadata": {
"id": "3sJ7LTpVFsqM"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"I understand, the Monty Hall Problem can be confusing! Let's run a simulation to see the results.\n",
"\n",
"I'll simulate 1,000 trials of the game and keep track of whether switching doors wins or loses. I'll then compare the results of switching and not switching.\n",
"\n",
"\n",
"``` python\n",
            "import random\n",
            "\n",
            "def play_monty_hall(switch):\n",
            "  \"\"\"Plays one round of the Monty Hall game and returns whether the player wins.\"\"\"\n",
            "  # Choose a random door for the car\n",
            "  car_door = random.randint(1, 3)\n",
            "\n",
            "  # Player picks a random door\n",
            "  player_choice = random.randint(1, 3)\n",
            "\n",
            "  # Host opens a door with a goat\n",
            "  if player_choice == car_door:\n",
            "    # Host opens a random door that's not the car door\n",
            "    host_reveal = random.choice([door for door in [1, 2, 3] if door != car_door])\n",
            "  else:\n",
            "    # Host opens the other door with a goat\n",
            "    host_reveal = [door for door in [1, 2, 3] if door != player_choice and door != car_door][0]\n",
            "\n",
            "  # Player switches doors\n",
            "  if switch:\n",
            "    player_choice = [door for door in [1, 2, 3] if door != player_choice and door != host_reveal][0]\n",
            "\n",
            "  # Player wins if they chose the car door\n",
            "  return player_choice == car_door\n",
            "\n",
            "# Run 1,000 trials\n",
            "num_trials = 1000\n",
            "\n",
            "# Track wins and losses\n",
            "switch_wins = 0\n",
            "switch_losses = 0\n",
            "stay_wins = 0\n",
            "stay_losses = 0\n",
            "\n",
            "for _ in range(num_trials):\n",
            "  # Switch doors\n",
            "  if play_monty_hall(switch=True):\n",
            "    switch_wins += 1\n",
            "  else:\n",
            "    switch_losses += 1\n",
            "\n",
            "  # Stay with original choice\n",
            "  if play_monty_hall(switch=False):\n",
            "    stay_wins += 1\n",
            "  else:\n",
            "    stay_losses += 1\n",
            "\n",
            "# Print the results\n",
            "print(f'Switching doors wins: {switch_wins}/{num_trials} ({switch_wins / num_trials * 100:.2f}%)')\n",
            "print(f'Switching doors losses: {switch_losses}/{num_trials} ({switch_losses / num_trials * 100:.2f}%)')\n",
            "print(f'Staying with original choice wins: {stay_wins}/{num_trials} ({stay_wins / num_trials * 100:.2f}%)')\n",
            "print(f'Staying with original choice losses: {stay_losses}/{num_trials} ({stay_losses / num_trials * 100:.2f}%)')\n",
            "\n",
            "```\n",
"```\n",
            "Switching doors wins: 658/1000 (65.80%)\n",
            "Switching doors losses: 342/1000 (34.20%)\n",
            "Staying with original choice wins: 339/1000 (33.90%)\n",
            "Staying with original choice losses: 661/1000 (66.10%)\n",
            "\n",
            "```\n",
"The simulation ran 1,000 times, and the results show that switching doors wins approximately 65.8% of the time, while staying with the original choice wins about 33.9% of the time.\n",
"\n",
"\n",
"This means that **switching doors is the much better strategy** in the Monty Hall Problem. \n",
"\n"
]
}
],
"source": [
"print(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "1a4c6e717f63"
},
"source": [
"## Next Steps\n",
"### Useful API references:\n",
"\n",
"Check the [Code execution documentation](https://ai.google.dev/gemini-api/docs/code-execution) for more details about the feature and in particular, the [recommendations](https://ai.google.dev/gemini-api/docs/code-execution?lang=python#code-execution-vs-function-calling) regarding when to use it instead of [function calling](https://ai.google.dev/gemini-api/docs/function-calling).\n",
"\n",
"### Continue your discovery of the Gemini API\n",
"\n",
"Learn how to control how the Gemini API can call your own functions using the [function calling](../quickstarts/Function_calling.ipynb) feature, or discover how to control the model output in [JSON](../quickstarts/JSON_mode.ipynb) or using an [Enum](../quickstarts/Enum.ipynb)."
]
}
],
"metadata": {
"colab": {
"collapsed_sections": [
"kQoJWW8lM48-"
],
"name": "Code_Execution.ipynb",
"toc_visible": true
},
"kernelspec": {
"display_name": "Python 3",
"name": "python3"
}
},
"nbformat": 4,
"nbformat_minor": 0
}
{
"cells": [
{
"cell_type": "markdown",
"metadata": {
"id": "Tce3stUlHN0L"
},
"source": [
"##### Copyright 2024 Google LLC."
]
},
{
"cell_type": "code",
"execution_count": 1,
"metadata": {
"cellView": "form",
"id": "tuOe1ymfHZPu"
},
"outputs": [],
"source": [
"# @title Licensed under the Apache License, Version 2.0 (the \"License\");\n",
"# you may not use this file except in compliance with the License.\n",
"# You may obtain a copy of the License at\n",
"#\n",
"# https://www.apache.org/licenses/LICENSE-2.0\n",
"#\n",
"# Unless required by applicable law or agreed to in writing, software\n",
"# distributed under the License is distributed on an \"AS IS\" BASIS,\n",
"# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.\n",
"# See the License for the specific language governing permissions and\n",
"# limitations under the License."
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "4BkXaeuqGFzD"
},
"source": [
"# Code Execution in the Gemini API\n",
"\n",
"<table align=\"left\">\n",
"  <td>\n",
"    <a target=\"_blank\" href=\"https://colab.research.google.com/github/google-gemini/cookbook/blob/main/quickstarts/Code_Execution.ipynb\"><img src=\"https://github.com/google-gemini/cookbook/blob/ce76bbe63554b4fceeba6bf6c2ef4b264d3d2da9/images/colab_logo_32px.png?raw=1\" />Run in Google Colab</a>\n",
"  </td>\n",
"</table>\n"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "CDhVGsAHhwG5"
},
"source": [
"The Gemini API [code execution](https://ai.google.dev/gemini-api/docs/code-execution) feature enables the model to generate and run Python code based on plain-text instructions that you give it. It can learn iteratively from the results until it arrives at a final output.\n",
"\n",
"This notebook is a walk through of how to use this feature."
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "kQoJWW8lM48-"
},
"source": [
"### Set up"
]
},
{
"cell_type": "code",
"execution_count": 2,
"metadata": {
"id": "6rshwediCXto"
},
"outputs": [
{
"name": "stdout",
"output_type": "stream",
"text": [
"\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m165.0/165.0 kB\u001b[0m \u001b[31m2.4 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
"\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m725.4/725.4 kB\u001b[0m \u001b[31m10.5 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
"\u001b[?25h"
]
}
],
"source": [
"!pip install -Uq \"google-generativeai>=0.7.2\""
]
},
{
"cell_type": "code",
"execution_count": 3,
"metadata": {
"id": "OsxWu_BI50Ex"
},
"outputs": [
{
"data": {
"application/vnd.google.colaboratory.intrinsic+json": {
"type": "string"
},
"text/plain": [
"'0.8.1'"
]
},
"execution_count": 3,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"import google.generativeai as genai\n",
"genai.__version__"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "b276ccf016b9"
},
"source": [
"To run the following cell, your API key must be stored it in a Colab Secret named `GOOGLE_API_KEY`. If you don't already have an API key, or you're not sure how to create a Colab Secret, see the [Authentication](https://github.com/google-gemini/cookbook/blob/main/quickstarts/Authentication.ipynb) quickstart for an example."
]
},
{
"cell_type": "code",
"execution_count": 4,
"metadata": {
"id": "itMjtruv7QqE"
},
"outputs": [],
"source": [
"from google.colab import userdata\n",
"genai.configure(api_key=userdata.get('GOOGLE_API_KEY'))"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "rvmIpRX5IN1q"
},
"source": [
"Tweak CSS for display in Colab"
]
},
{
"cell_type": "code",
"execution_count": 5,
"metadata": {
"id": "kS3JQzazOI48"
},
"outputs": [],
"source": [
"from IPython.display import HTML, Markdown\n",
"\n",
"def set_css_in_cell_output(unused):\n",
"  display(HTML(\"\"\"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>\"\"\"))\n",
"\n",
"get_ipython().events.register('pre_run_cell', set_css_in_cell_output)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "q-jdBwXlM67j"
},
"source": [
"## Pass `\"code_execution\"` as a `tool`\n",
"\n",
"When initiating the model, pass `\"code_execution\"` as a `tool` to tell the model that it is allowed (but not forced) to generate and run code."
]
},
{
"cell_type": "code",
"execution_count": 6,
"metadata": {
"id": "BFxIcGkxbq3_"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"model = genai.GenerativeModel(model_name='gemini-1.5-flash', tools=\"code_execution\")"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "mZgn5tm-NCfH"
},
"source": [
"## Call `generate_content`"
]
},
{
"cell_type": "code",
"execution_count": 7,
"metadata": {
"id": "u2DRvZZde2C6"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"result = model.generate_content(\"What is the sum of the first 50 prime numbers?\"\n",
"                                \"Generate and run code for the calculation, and make sure you get all 50.\")"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "8uJ-Fk1I_AH8"
},
"source": [
"The model returns a list of parts including `text`, `executable_code`, and `execution_result` parts."
]
},
{
"cell_type": "code",
"execution_count": 8,
"metadata": {
"id": "E1_KEd4P-_YB"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/plain": [
"[['text'], ['executable_code'], ['code_execution_result'], ['text']]"
]
},
"execution_count": 8,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"[\n",
"    list(type(p).to_dict(p))\n",
"    for p in result.candidates[0].content.parts\n",
"]"
]
},
{
"cell_type": "code",
"execution_count": 9,
"metadata": {
"id": "JtL3wwKJA0Jf"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"text: \"I will determine the sum of the first 50 prime numbers. \\n\\nFirst, I need to define what a prime number is. A prime number is a whole number greater than 1 that has only two divisors: 1 and itself. \\n\\nTo calculate the sum of the first 50 prime numbers, we can use the following Python code:\\n\\n\"\n",
"\n",
"\n",
"executable_code {\n",
"  language: PYTHON\n",
"  code: \"\\ndef is_prime(num):\\n    \\\"\\\"\\\"\\n    Checks if a number is prime.\\n    \\\"\\\"\\\"\\n    if num <= 1:\\n        return False\\n    for i in range(2, int(num**0.5) + 1):\\n        if num % i == 0:\\n            return False\\n    return True\\n\\n\\ndef find_primes(n):\\n    \\\"\\\"\\\"\\n    Generates a list of the first n prime numbers.\\n    \\\"\\\"\\\"\\n    primes = []\\n    count = 0\\n    num = 2\\n    while count < n:\\n        if is_prime(num):\\n            primes.append(num)\\n            count += 1\\n        num += 1\\n    return primes\\n\\n\\nprimes = find_primes(50)\\nsum_primes = sum(primes)\\n\\nprint(f\\\"The sum of the first 50 prime numbers is: {sum_primes}\\\")\\n\"\n",
"}\n",
"\n",
"\n",
"code_execution_result {\n",
"  outcome: OUTCOME_OK\n",
"  output: \"The sum of the first 50 prime numbers is: 5117\\n\"\n",
"}\n",
"\n",
"\n",
"text: \"The code first defines two functions: `is_prime` and `find_primes`. `is_prime` takes a number as input and returns `True` if the number is prime and `False` otherwise. It checks if the number is less than or equal to 1, in which case it is not prime. It then iterates through all numbers from 2 up to the square root of the input number. For each number, it checks if the input number is divisible by the current number. If it is, then the number is not prime and the function returns `False`. Otherwise, it continues to the next number. If the function reaches the end of the loop without returning `False`, then the number is prime and the function returns `True`.\\n\\n`find_primes` takes an integer `n` as input and returns a list of the first `n` prime numbers. It initializes an empty list `primes` and a counter `count` to 0. It then iterates through all numbers starting from 2. For each number, it calls the `is_prime` function to check if the number is prime. If it is, it appends the number to the `primes` list and increments the counter by 1. The loop continues until the counter reaches `n`. Finally, the function returns the `primes` list.\\n\\nThe code then calls the `find_primes` function with the argument 50 to get a list of the first 50 prime numbers. It then calls the `sum` function on the list to get the sum of all the elements in the list, which is the sum of the first 50 prime numbers. Finally, it prints the sum to the console.\\n\\nThe code successfully calculates the sum of the first 50 prime numbers, which is 5117.\"\n",
"\n",
"\n"
]
}
],
"source": [
"for part in result.candidates[0].content.parts:\n",
"  print(part)\n",
"  print()"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "TOKHOJQ6_LZO"
},
"source": [
"The `.text` property formats the parts into Markdown compatible text:"
]
},
{
"cell_type": "code",
"execution_count": 10,
"metadata": {
"id": "Qe_aoIGoMlMc"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"I will determine the sum of the first 50 prime numbers. \n",
"\n",
"First, I need to define what a prime number is. A prime number is a whole number greater than 1 that has only two divisors: 1 and itself. \n",
"\n",
"To calculate the sum of the first 50 prime numbers, we can use the following Python code:\n",
"\n",
"\n",
"``` python\n",
            "def is_prime(num):\n",
            "    \"\"\"\n",
            "    Checks if a number is prime.\n",
            "    \"\"\"\n",
            "    if num <= 1:\n",
            "        return False\n",
            "    for i in range(2, int(num**0.5) + 1):\n",
            "        if num % i == 0:\n",
            "            return False\n",
            "    return True\n",
            "\n",
            "\n",
            "def find_primes(n):\n",
            "    \"\"\"\n",
            "    Generates a list of the first n prime numbers.\n",
            "    \"\"\"\n",
            "    primes = []\n",
            "    count = 0\n",
            "    num = 2\n",
            "    while count < n:\n",
            "        if is_prime(num):\n",
            "            primes.append(num)\n",
            "            count += 1\n",
            "        num += 1\n",
            "    return primes\n",
            "\n",
            "\n",
            "primes = find_primes(50)\n",
            "sum_primes = sum(primes)\n",
            "\n",
            "print(f\"The sum of the first 50 prime numbers is: {sum_primes}\")\n",
            "\n",
            "```\n",
"```\n",
            "The sum of the first 50 prime numbers is: 5117\n",
            "\n",
            "```\n",
"The code first defines two functions: `is_prime` and `find_primes`. `is_prime` takes a number as input and returns `True` if the number is prime and `False` otherwise. It checks if the number is less than or equal to 1, in which case it is not prime. It then iterates through all numbers from 2 up to the square root of the input number. For each number, it checks if the input number is divisible by the current number. If it is, then the number is not prime and the function returns `False`. Otherwise, it continues to the next number. If the function reaches the end of the loop without returning `False`, then the number is prime and the function returns `True`.\n",
"\n",
"`find_primes` takes an integer `n` as input and returns a list of the first `n` prime numbers. It initializes an empty list `primes` and a counter `count` to 0. It then iterates through all numbers starting from 2. For each number, it calls the `is_prime` function to check if the number is prime. If it is, it appends the number to the `primes` list and increments the counter by 1. The loop continues until the counter reaches `n`. Finally, the function returns the `primes` list.\n",
"\n",
"The code then calls the `find_primes` function with the argument 50 to get a list of the first 50 prime numbers. It then calls the `sum` function on the list to get the sum of all the elements in the list, which is the sum of the first 50 prime numbers. Finally, it prints the sum to the console.\n",
"\n",
"The code successfully calculates the sum of the first 50 prime numbers, which is 5117.\n"
]
}
],
"source": [
"print(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "hxfUg10DOxgE"
},
"source": [
"In a notebook you can display the Markdown:"
]
},
{
"cell_type": "code",
"execution_count": 11,
"metadata": {
"id": "N-c7VXWoEFQB"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "I will determine the sum of the first 50 prime numbers. \n\nFirst, I need to define what a prime number is. A prime number is a whole number greater than 1 that has only two divisors: 1 and itself. \n\nTo calculate the sum of the first 50 prime numbers, we can use the following Python code:\n\n\n``` python\ndef is_prime(num):\n    \"\"\"\n    Checks if a number is prime.\n    \"\"\"\n    if num <= 1:\n        return False\n    for i in range(2, int(num**0.5) + 1):\n        if num % i == 0:\n            return False\n    return True\n\n\ndef find_primes(n):\n    \"\"\"\n    Generates a list of the first n prime numbers.\n    \"\"\"\n    primes = []\n    count = 0\n    num = 2\n    while count < n:\n        if is_prime(num):\n            primes.append(num)\n            count += 1\n        num += 1\n    return primes\n\n\nprimes = find_primes(50)\nsum_primes = sum(primes)\n\nprint(f\"The sum of the first 50 prime numbers is: {sum_primes}\")\n\n```\n```\nThe sum of the first 50 prime numbers is: 5117\n\n```\nThe code first defines two functions: `is_prime` and `find_primes`. `is_prime` takes a number as input and returns `True` if the number is prime and `False` otherwise. It checks if the number is less than or equal to 1, in which case it is not prime. It then iterates through all numbers from 2 up to the square root of the input number. For each number, it checks if the input number is divisible by the current number. If it is, then the number is not prime and the function returns `False`. Otherwise, it continues to the next number. If the function reaches the end of the loop without returning `False`, then the number is prime and the function returns `True`.\n\n`find_primes` takes an integer `n` as input and returns a list of the first `n` prime numbers. It initializes an empty list `primes` and a counter `count` to 0. It then iterates through all numbers starting from 2. For each number, it calls the `is_prime` function to check if the number is prime. If it is, it appends the number to the `primes` list and increments the counter by 1. The loop continues until the counter reaches `n`. Finally, the function returns the `primes` list.\n\nThe code then calls the `find_primes` function with the argument 50 to get a list of the first 50 prime numbers. It then calls the `sum` function on the list to get the sum of all the elements in the list, which is the sum of the first 50 prime numbers. Finally, it prints the sum to the console.\n\nThe code successfully calculates the sum of the first 50 prime numbers, which is 5117.",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 11,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"from IPython.display import Markdown\n",
"Markdown(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "avyoRa0XF5wR"
},
"source": [
"Note: you can also set the `tools` argument on the call to `generate_content`:"
]
},
{
"cell_type": "code",
"execution_count": 12,
"metadata": {
"id": "DL2mRlNTF5JN"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"model2 = genai.GenerativeModel(model_name='gemini-1.5-flash')"
]
},
{
"cell_type": "code",
"execution_count": 13,
"metadata": {
"id": "fY062-nsGLBu"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"response = model2.generate_content(\n",
"    \"Write code to count how many letter r in the word strawberry\",\n",
"    tools=\"code_execution\")"
]
},
{
"cell_type": "code",
"execution_count": 14,
"metadata": {
"id": "fQY1_501GfP-"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "\n``` python\nword = \"strawberry\"\ncount = 0\nfor letter in word:\n  if letter == \"r\":\n    count += 1\nprint(f'There are {count} letter \"r\" in the word \"strawberry\"')\n\n```\n```\nThere are 3 letter \"r\" in the word \"strawberry\"\n\n```\nI iterated over each letter in the word \"strawberry\" and counted how many times the letter \"r\" appears. The code counted 3 \"r\"s in the word \"strawberry\". \n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 14,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"Markdown(response.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "4QTF9Lk6Ds-b"
},
"source": [
"## Chat\n",
"\n",
"It works the same when using a `chat`:"
]
},
{
"cell_type": "code",
"execution_count": 15,
"metadata": {
"id": "_19QkCnQEZSu"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
}
],
"source": [
"chat = model.start_chat()"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "9b2d47bf0927"
},
"source": [
"This time, you're going to ask the model to use a [Bogo-sort](https://en.wikipedia.org/wiki/Bogosort) algorithm to sort a list of numbers."
]
},
{
"cell_type": "code",
"execution_count": 16,
"metadata": {
"id": "VFMAiEH_Dx6E"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "\n``` python\nimport random\n\ndef bogo_sort(list_):\n    while not is_sorted(list_):\n        random.shuffle(list_)\n    return list_\n\ndef is_sorted(list_):\n    for i in range(len(list_) - 1):\n        if list_[i] > list_[i + 1]:\n            return False\n    return True\n\nlist_ = [2, 34, 1, 65, 4]\nsorted_list = bogo_sort(list_.copy())\nprint(f'Sorted list: {sorted_list}')\n\n```\n```\nSorted list: [1, 2, 4, 34, 65]\n\n```\nBogo sort is a very inefficient sorting algorithm that relies on random shuffling of the list until the list is sorted.  I have implemented the bogo sort algorithm using the `random.shuffle` function, which randomly shuffles the list until the list is sorted.  The sorted list is outputted: `[1, 2, 4, 34, 65]`.  It is important to note that this solution is not recommended for practical use as it has a time complexity of O(n!), making it extremely inefficient for even small lists.  There are many much faster and more efficient sorting algorithms available. \n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 16,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"response = chat.send_message(\"Can you run some code to bogo-sort this list of numbers?: [2,34,1,65,4]\")\n",
"Markdown(response.text)"
]
},
{
"cell_type": "code",
"execution_count": 25,
"metadata": {
"id": "ANxrYfl0Bk6T"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "\n``` python\nimport random\n\ndef bogo_sort(list_):\n    iterations = 0\n    while not is_sorted(list_):\n        random.shuffle(list_)\n        iterations += 1\n    return list_, iterations\n\ndef is_sorted(list_):\n    for i in range(len(list_) - 1):\n        if list_[i] > list_[i + 1]:\n            return False\n    return True\n\nlist_ = [2, 34, 1, 65, 4]\nsorted_list, iterations = bogo_sort(list_.copy())\nprint(f'Sorted list: {sorted_list}')\nprint(f'Iterations: {iterations}')\n\n```\n```\nSorted list: [1, 2, 4, 34, 65]\nIterations: 83\n\n```\nI've added a counter variable `iterations` to the `bogo_sort` function to track the number of shuffles. It took **83 iterations** to sort the list in this run.  \n\nRemember, bogo sort is extremely inefficient. The number of iterations can fluctuate wildly depending on the initial order of the list and how the random shuffling occurs.  It's unlikely to be a practical choice for real-world sorting tasks.\n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 25,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"response = chat.send_message(\"Modify the code to count the number of iterations. How many iterations does it take?\")\n",
"Markdown(response.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "69fc4457ffd4"
},
"source": [
"Try running the previous cell multiple times and you'll see a different number of iterations, indicating that the Gemini API indeed ran the code and obtained different results due to the nature of the algorithm."
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "tQXlC1FdEnXH"
},
"source": [
"## Multimedia"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "_3PKhsYvF4Hs"
},
"source": [
"You can pass media objects as part of the prompt, the model can look at these objects but it can't use them in the code."
]
},
{
"cell_type": "code",
"execution_count": 18,
"metadata": {
"id": "bDg1bDRpAnFR"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current\n",
"                                 Dload  Upload   Total   Spent    Left  Speed\n",
"100 24719  100 24719    0     0   134k      0 --:--:-- --:--:-- --:--:--  134k\n"
]
}
],
"source": [
"! curl -o montey_hall.png https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Monty_open_door.svg/640px-Monty_open_door.svg.png"
]
},
{
"cell_type": "code",
"execution_count": 19,
"metadata": {
"id": "1Uhq7nZPEsvO"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"image/png": "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\n",
"text/plain": [
"<PIL.PngImagePlugin.PngImageFile image mode=RGBA size=640x356>"
]
},
"execution_count": 19,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"from PIL import Image\n",
"montey_hall_image = Image.open(\"montey_hall.png\")\n",
"montey_hall_image"
]
},
{
"cell_type": "code",
"execution_count": 20,
"metadata": {
"id": "2S0WIddTEzUm"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"data": {
"text/markdown": "I understand. The Monty Hall problem is a classic probability puzzle that often leads to counterintuitive conclusions. Let's run a simulation in Python to see how the odds play out.\n\n\n``` python\nimport random\n\ndef monty_hall(switch):\n  \"\"\"Simulates a single round of the Monty Hall problem.\"\"\"\n  doors = [0, 1, 2]\n  car_door = random.choice(doors)\n  initial_choice = random.choice(doors)\n\n  # Host reveals a goat\n  if initial_choice != car_door:\n    host_reveal = random.choice([d for d in doors if d != initial_choice and d != car_door])\n  else:\n    host_reveal = random.choice([d for d in doors if d != initial_choice])\n\n  # Switch or stay\n  if switch:\n    final_choice = [d for d in doors if d != initial_choice and d != host_reveal][0]\n  else:\n    final_choice = initial_choice\n\n  return final_choice == car_door\n\ndef run_trials(trials, switch):\n  \"\"\"Runs a set of Monty Hall trials with the specified switch strategy.\"\"\"\n  wins = 0\n  for _ in range(trials):\n    if monty_hall(switch):\n      wins += 1\n  return wins / trials\n\n# Run simulations\ntrials = 1000\nstay_win_rate = run_trials(trials, switch=False)\nswitch_win_rate = run_trials(trials, switch=True)\n\nprint(f\"Win rate staying: {stay_win_rate * 100:.2f}%\")\nprint(f\"Win rate switching: {switch_win_rate * 100:.2f}%\")\n\n```\n```\nWin rate staying: 32.60%\nWin rate switching: 66.90%\n\n```\nThe simulation results show that switching doors significantly increases your chances of winning the car. The win rate for staying is around 33%, while the win rate for switching is around 67%. This confirms the counterintuitive but mathematically proven result of the Monty Hall problem: switching doors doubles your chances of winning. \n",
"text/plain": [
"<IPython.core.display.Markdown object>"
]
},
"execution_count": 20,
"metadata": {},
"output_type": "execute_result"
}
],
"source": [
"prompt=\"\"\"\n",
"Run a simulation of the Monty Hall Problem with 1,000 trials.\n",
"\n",
"\n",
"Here's how this works as a reminder. In the Monty Hall Problem, you're on a game\n",
"show with three doors. Behind one is a car, and behind the others are goats. You\n",
"pick a door. The host, who knows what's behind the doors, opens a different door\n",
"to reveal a goat. Should you switch to the remaining unopened door?\n",
"\n",
"\n",
"The answer has always been a little difficult for me to understand when people\n",
"solve it with math - so please run a simulation with Python to show me what the\n",
"best strategy is.\n",
"\n",
"\n",
"Thank you!\n",
"\"\"\"\n",
"result = model.generate_content([montey_hall_image, prompt])\n",
"Markdown(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "nFZ3XoCRGnhO"
},
"source": [
"## Streaming"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "crv9H7euGuqP"
},
"source": [
"Streaming is compatible with code execution. Just note that successive parts of the same type (`text`, `executable_code` or `execution_result`) are meant to be joined together:"
]
},
{
"cell_type": "code",
"execution_count": 21,
"metadata": {
"id": "J9s8DPy7GuKN"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"text: \"I understand\"\n",
"\n",
"----------------------------------------\n",
"text: \", the Monty Hall Problem can be confusing! Let\\'s run a simulation to see\"\n",
"\n",
"----------------------------------------\n",
"text: \" the results.\\n\\nI\\'ll simulate 1,000 trials of the\"\n",
"\n",
"----------------------------------------\n",
"text: \" game and keep track of whether switching doors wins or loses. I\\'ll then compare the results of switching and not switching.\\n\\n\"\n",
"\n",
"----------------------------------------\n",
"executable_code {\n",
"  language: PYTHON\n",
"  code: \"\\nimport random\\n\\ndef play_monty_hall(switch):\\n  \\\"\\\"\\\"Plays one round of the Monty Hall game and returns whether the player wins.\\\"\\\"\\\"\\n  # Choose a random door for the car\\n  car_door = random.randint(1, 3)\\n\\n  # Player picks a random door\\n  player_choice = random.randint(1, 3)\\n\\n  # Host opens a door with a goat\\n  if player_choice == car_door:\\n    # Host opens a random door that\\'s not the car door\\n    host_reveal = random.choice([door for door in [1, 2, 3] if door != car_door])\\n  else:\\n    # Host opens the other door with a goat\\n    host_reveal = [door for door in [1, 2, 3] if door != player_choice and door != car_door][0]\\n\\n  # Player switches doors\\n  if switch:\\n    player_choice = [door for door in [1, 2, 3] if door != player_choice and door != host_reveal][0]\\n\\n  # Player wins if they chose the car door\\n  return player_choice == car_door\\n\\n# Run 1,000 trials\\nnum_trials = 1000\\n\\n# Track wins and losses\\nswitch_wins = 0\\nswitch_losses = 0\\nstay_wins = 0\\nstay_losses = 0\\n\\nfor _ in range(num_trials):\\n  # Switch doors\\n  if play_monty_hall(switch=True):\\n    switch_wins += 1\\n  else:\\n    switch_losses += 1\\n\\n  # Stay with original choice\\n  if play_monty_hall(switch=False):\\n    stay_wins += 1\\n  else:\\n    stay_losses += 1\\n\\n# Print the results\\nprint(f\\'Switching doors wins: {switch_wins}/{num_trials} ({switch_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Switching doors losses: {switch_losses}/{num_trials} ({switch_losses / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice wins: {stay_wins}/{num_trials} ({stay_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice losses: {stay_losses}/{num_trials} ({stay_losses / num_trials * 100:.2f}%)\\')\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"code_execution_result {\n",
"  outcome: OUTCOME_OK\n",
"  output: \"Switching doors wins: 658/1000 (65.80%)\\nSwitching doors losses: 342/1000 (34.20%)\\nStaying with original choice wins: 339/1000 (33.90%)\\nStaying with original choice losses: 661/1000 (66.10%)\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"text: \"The\"\n",
"\n",
"----------------------------------------\n",
"text: \" simulation ran 1,000 times, and the results show that switching\"\n",
"\n",
"----------------------------------------\n",
"text: \" doors wins approximately 65.8% of the time, while staying with\"\n",
"\n",
"----------------------------------------\n",
"text: \" the original choice wins about 33.9% of the time.\\n\\n\\nThis means that **switching doors is the much better strategy** in the Monty Hall\"\n",
"\n",
"----------------------------------------\n",
"text: \" Problem. \\n\"\n",
"\n",
"----------------------------------------\n"
]
}
],
"source": [
"result = model.generate_content([montey_hall_image, prompt], stream=True)\n",
"for chunk in result:\n",
"  print(chunk.candidates[0].content.parts[0])\n",
"  print('----------------------------------------')"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "QvIoEpQyifU_"
},
"source": [
"The result object automatically joins the parts, as you iterate over them:"
]
},
{
"cell_type": "code",
"execution_count": 22,
"metadata": {
"id": "yjUSubFXiaEP"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"text: \"I understand, the Monty Hall Problem can be confusing! Let\\'s run a simulation to see the results.\\n\\nI\\'ll simulate 1,000 trials of the game and keep track of whether switching doors wins or loses. I\\'ll then compare the results of switching and not switching.\\n\\n\"\n",
"\n",
"----------------------------------------\n",
"executable_code {\n",
"  language: PYTHON\n",
"  code: \"\\nimport random\\n\\ndef play_monty_hall(switch):\\n  \\\"\\\"\\\"Plays one round of the Monty Hall game and returns whether the player wins.\\\"\\\"\\\"\\n  # Choose a random door for the car\\n  car_door = random.randint(1, 3)\\n\\n  # Player picks a random door\\n  player_choice = random.randint(1, 3)\\n\\n  # Host opens a door with a goat\\n  if player_choice == car_door:\\n    # Host opens a random door that\\'s not the car door\\n    host_reveal = random.choice([door for door in [1, 2, 3] if door != car_door])\\n  else:\\n    # Host opens the other door with a goat\\n    host_reveal = [door for door in [1, 2, 3] if door != player_choice and door != car_door][0]\\n\\n  # Player switches doors\\n  if switch:\\n    player_choice = [door for door in [1, 2, 3] if door != player_choice and door != host_reveal][0]\\n\\n  # Player wins if they chose the car door\\n  return player_choice == car_door\\n\\n# Run 1,000 trials\\nnum_trials = 1000\\n\\n# Track wins and losses\\nswitch_wins = 0\\nswitch_losses = 0\\nstay_wins = 0\\nstay_losses = 0\\n\\nfor _ in range(num_trials):\\n  # Switch doors\\n  if play_monty_hall(switch=True):\\n    switch_wins += 1\\n  else:\\n    switch_losses += 1\\n\\n  # Stay with original choice\\n  if play_monty_hall(switch=False):\\n    stay_wins += 1\\n  else:\\n    stay_losses += 1\\n\\n# Print the results\\nprint(f\\'Switching doors wins: {switch_wins}/{num_trials} ({switch_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Switching doors losses: {switch_losses}/{num_trials} ({switch_losses / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice wins: {stay_wins}/{num_trials} ({stay_wins / num_trials * 100:.2f}%)\\')\\nprint(f\\'Staying with original choice losses: {stay_losses}/{num_trials} ({stay_losses / num_trials * 100:.2f}%)\\')\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"code_execution_result {\n",
"  outcome: OUTCOME_OK\n",
"  output: \"Switching doors wins: 658/1000 (65.80%)\\nSwitching doors losses: 342/1000 (34.20%)\\nStaying with original choice wins: 339/1000 (33.90%)\\nStaying with original choice losses: 661/1000 (66.10%)\\n\"\n",
"}\n",
"\n",
"----------------------------------------\n",
"text: \"The simulation ran 1,000 times, and the results show that switching doors wins approximately 65.8% of the time, while staying with the original choice wins about 33.9% of the time.\\n\\n\\nThis means that **switching doors is the much better strategy** in the Monty Hall Problem. \\n\"\n",
"\n",
"----------------------------------------\n"
]
}
],
"source": [
"for part in result.candidates[0].content.parts:\n",
"  print(part)\n",
"  print('----------------------------------------')"
]
},
{
"cell_type": "code",
"execution_count": 23,
"metadata": {
"id": "3sJ7LTpVFsqM"
},
"outputs": [
{
"data": {
"text/html": [
"<style>\n",
"div.output_markdown {\n",
"  font-size: 16px\n",
"}\n",
"\n",
"div.output_markdown pre code {\n",
"  color: #222222;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(even) {\n",
"  background: #CCCCCC;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"\n",
"div.output_markdown pre:nth-of-type(odd) {\n",
"  background: #BBBBEE;\n",
"  margin: 16px;\n",
"  padding: 16px;\n",
"}\n",
"</style>"
],
"text/plain": [
"<IPython.core.display.HTML object>"
]
},
"metadata": {},
"output_type": "display_data"
},
{
"name": "stdout",
"output_type": "stream",
"text": [
"I understand, the Monty Hall Problem can be confusing! Let's run a simulation to see the results.\n",
"\n",
"I'll simulate 1,000 trials of the game and keep track of whether switching doors wins or loses. I'll then compare the results of switching and not switching.\n",
"\n",
"\n",
"``` python\n",
            "import random\n",
            "\n",
            "def play_monty_hall(switch):\n",
            "  \"\"\"Plays one round of the Monty Hall game and returns whether the player wins.\"\"\"\n",
            "  # Choose a random door for the car\n",
            "  car_door = random.randint(1, 3)\n",
            "\n",
            "  # Player picks a random door\n",
            "  player_choice = random.randint(1, 3)\n",
            "\n",
            "  # Host opens a door with a goat\n",
            "  if player_choice == car_door:\n",
            "    # Host opens a random door that's not the car door\n",
            "    host_reveal = random.choice([door for door in [1, 2, 3] if door != car_door])\n",
            "  else:\n",
            "    # Host opens the other door with a goat\n",
            "    host_reveal = [door for door in [1, 2, 3] if door != player_choice and door != car_door][0]\n",
            "\n",
            "  # Player switches doors\n",
            "  if switch:\n",
            "    player_choice = [door for door in [1, 2, 3] if door != player_choice and door != host_reveal][0]\n",
            "\n",
            "  # Player wins if they chose the car door\n",
            "  return player_choice == car_door\n",
            "\n",
            "# Run 1,000 trials\n",
            "num_trials = 1000\n",
            "\n",
            "# Track wins and losses\n",
            "switch_wins = 0\n",
            "switch_losses = 0\n",
            "stay_wins = 0\n",
            "stay_losses = 0\n",
            "\n",
            "for _ in range(num_trials):\n",
            "  # Switch doors\n",
            "  if play_monty_hall(switch=True):\n",
            "    switch_wins += 1\n",
            "  else:\n",
            "    switch_losses += 1\n",
            "\n",
            "  # Stay with original choice\n",
            "  if play_monty_hall(switch=False):\n",
            "    stay_wins += 1\n",
            "  else:\n",
            "    stay_losses += 1\n",
            "\n",
            "# Print the results\n",
            "print(f'Switching doors wins: {switch_wins}/{num_trials} ({switch_wins / num_trials * 100:.2f}%)')\n",
            "print(f'Switching doors losses: {switch_losses}/{num_trials} ({switch_losses / num_trials * 100:.2f}%)')\n",
            "print(f'Staying with original choice wins: {stay_wins}/{num_trials} ({stay_wins / num_trials * 100:.2f}%)')\n",
            "print(f'Staying with original choice losses: {stay_losses}/{num_trials} ({stay_losses / num_trials * 100:.2f}%)')\n",
            "\n",
            "```\n",
"```\n",
            "Switching doors wins: 658/1000 (65.80%)\n",
            "Switching doors losses: 342/1000 (34.20%)\n",
            "Staying with original choice wins: 339/1000 (33.90%)\n",
            "Staying with original choice losses: 661/1000 (66.10%)\n",
            "\n",
            "```\n",
"The simulation ran 1,000 times, and the results show that switching doors wins approximately 65.8% of the time, while staying with the original choice wins about 33.9% of the time.\n",
"\n",
"\n",
"This means that **switching doors is the much better strategy** in the Monty Hall Problem. \n",
"\n"
]
}
],
"source": [
"print(result.text)"
]
},
{
"cell_type": "markdown",
"metadata": {
"id": "1a4c6e717f63"
},
"source": [
"## Next Steps\n",
"### Useful API references:\n",
"\n",
"Check the [Code execution documentation](https://ai.google.dev/gemini-api/docs/code-execution) for more details about the feature and in particular, the [recommendations](https://ai.google.dev/gemini-api/docs/code-execution?lang=python#code-execution-vs-function-calling) regarding when to use it instead of [function calling](https://ai.google.dev/gemini-api/docs/function-calling).\n",
"\n",
"### Continue your discovery of the Gemini API\n",
"\n",
"Learn how to control how the Gemini API can call your own functions using the [function calling](../quickstarts/Function_calling.ipynb) feature, or discover how to control the model output in [JSON](../quickstarts/JSON_mode.ipynb) or using an [Enum](../quickstarts/Enum.ipynb)."
]
}
],
"metadata": {
"colab": {
"collapsed_sections": [
"kQoJWW8lM48-"
],
"name": "Code_Execution.ipynb",
"toc_visible": true
},
"kernelspec": {
"display_name": "Python 3",
"name": "python3"
}
},
"nbformat": 4,
"nbformat_minor": 0
}
import 'package:flutter/material.dart';
import 'dart:math';

class AlienTechCover {
static Widget generate(String textInput) {
List<String> keywords = textInput.split(' ');

    // Color logic
    Color baseColor = Colors.green;
    if (keywords.contains('blue')) baseColor = Colors.blue;
    if (keywords.contains('red')) baseColor = Colors.red;

    int numLines = keywords.length + 5;

    List<Widget> stackChildren = [
      // Circuit Lines
      for (int i = 0; i < numLines; i++)
        Positioned(
          left: Random().nextDouble() * 300,
          top: Random().nextDouble() * 300,
          child: Container(
            width: Random().nextDouble() * 50 + 10,
            height: 2,
            color: baseColor.shade200.withOpacity(0.5),
          ),
        ),
      // Central Glow
      Center(
        child: Container(
          width: 80,
          height: 80,
          decoration: BoxDecoration(
            color: baseColor.shade400.withOpacity(0.7),
            shape: BoxShape.circle,
            boxShadow: [
              BoxShadow(
                color: baseColor.shade400,
                blurRadius: 20,
                spreadRadius: 5,
              ),
            ],
          ),
        ),
      ),
      // Hexagon Pattern
      for (int i = 0; i < 5; i++)
        Positioned(
          left: Random().nextDouble() * 300,
          top: Random().nextDouble() * 300,
          child: Transform.rotate(
            angle: Random().nextDouble() * pi * 2,
            child: CustomPaint(
              size: Size(20, (20 * 0.8660254037844386)),
              painter: HexagonPainter(color: baseColor.shade300.withOpacity(0.6)),
            ),
          ),
        ),
      // Additional visual: energy pulse if "energy" keyword is present
      if (keywords.contains('energy'))
        Center(
          child: Container(
            width: 120,
            height: 120,
            decoration: BoxDecoration(
              shape: BoxShape.circle,
              gradient: RadialGradient(
                colors: [
                  baseColor.shade100.withOpacity(0.2),
                  baseColor.shade400.withOpacity(0.05),
                  Colors.transparent,
                ],
                stops: [0.5, 0.8, 1.0],
              ),
            ),
          ),
        ),
      // Additional visual: field effect if "field" keyword is present
      if (keywords.contains('field'))
        Positioned.fill(
          child: IgnorePointer(
            child: Container(
              decoration: BoxDecoration(
                gradient: SweepGradient(
                  colors: [
                    baseColor.shade100.withOpacity(0.1),
                    baseColor.shade400.withOpacity(0.15),
                    baseColor.shade100.withOpacity(0.1),
                  ],
                  stops: [0.0, 0.5, 1.0],
                ),
              ),
            ),
          ),
        ),
      // Additional visual: core ring if "core" keyword is present
      if (keywords.contains('core'))
        Center(
          child: Container(
            width: 100,
            height: 100,
            decoration: BoxDecoration(
              shape: BoxShape.circle,
              border: Border.all(
                color: baseColor.shade200.withOpacity(0.5),
                width: 6,
              ),
            ),
          ),
        ),
    ];

    return Container(
      decoration: BoxDecoration(
        color: baseColor.shade900,
      ),
      child: Stack(
        children: stackChildren,
      ),
    );
}
}

class HexagonPainter extends CustomPainter {
final Color color;
HexagonPainter({required this.color});

@override
void paint(Canvas canvas, Size size) {
final path = Path();
final height = size.height;
final width = size.width;

    path.moveTo(size.width / 2, 0);
    path.lineTo(width, height * 0.25);
    path.lineTo(width, height * 0.75);
    path.lineTo(size.width / 2, height);
    path.lineTo(0, height * 0.75);
    path.lineTo(0, height * 0.25);
    path.close();

    final paint = Paint()
      ..color = color
      ..style = PaintingStyle.fill;

    canvas.drawPath(path, paint);
}

@override
bool shouldRepaint(covariant CustomPainter oldDelegate) {
return false;
}
}class HexagonPainter extends CustomPainter {
final Color color;
HexagonPainter({required this.color});

@override
void paint(Canvas canvas, Size size) {
final path = Path();
final height = size.height;
final width = size.width;

    path.moveTo(size.width / 2, 0);
    path.lineTo(width, height * 0.25);
    path.lineTo(width, height * 0.75);
    path.lineTo(size.width / 2, height);
    path.lineTo(0, height * 0.75);
    path.lineTo(0, height * 0.25);
    path.close();

    final paint = Paint()
      ..color = color
      ..style = PaintingStyle.fill;

    canvas.drawPath(path, paint);
}

@override
bool shouldRepaint(covariant CustomPainter oldDelegate) {
return false;
}
}return Container(
decoration: BoxDecoration(
color: baseColor.shade900, // Dark background
),
child: Stack(
children: [
// Circuit Lines
for (int i = 0; i < numLines; i++)
Positioned(
left: Random().nextDouble() * 300,
top: Random().nextDouble() * 300,
child: Container(
width: Random().nextDouble() * 50 + 10,
height: 2,
color: baseColor.shade200.withOpacity(0.5), // Glowing line
),
),
// Central Glow
Center(
child: Container(
width: 80,
height: 80,
decoration: BoxDecoration(
color: baseColor.shade400.withOpacity(0.7),
shape: BoxShape.circle,
boxShadow: [
BoxShadow(
color: baseColor.shade400,
blurRadius: 20,
spreadRadius: 5,
),
],
),
),
),
// Hexagon Pattern
for (int i = 0; i < 5; i++)
Positioned(
left: Random().nextDouble() * 300,
top: Random().nextDouble() * 300,
child: Transform.rotate(
angle: Random().nextDouble() * pi * 2,
child: CustomPaint(
size: Size(20, (20 * 0.8660254037844386)), // Hexagon
painter: HexagonPainter(color: baseColor.shade300.withOpacity(0.6)),
),
),
),
],
),
);int numLines = keywords.length + 5;List<String> keywords = textInput.split(' ');
task copyTask(type: Copy) {
from 'src/main/webapp'
into 'build/explodedWar'
include "*.*"
}apply plugin: MyPlugin
class MyPlugin implements Plugin<Project> {
@Override
void apply(Project project) {
project.task('copyTask', type: Copy) {
from 'src/main/webapp'
into 'build/explodedWar'
include "*.*"
}
}
}def rootProjDir = "${rootDir}/../../"
...
def assembleTask = variant.getAssembleProvider()
def mustRunAfterTaskName = "create${variant.name.capitalize()}ApkListingFileRedirect"
def newTargetName = "${theAppName}-v${variant.versionName}-${variant.name}.apk"
def copyTask = project.tasks.register("copyAndRenameOutputAPKFile${assembleTask.name.capitalize()}") {
mustRunAfter(mustRunAfterTaskName)
doLast {
copy {
from outputFile.parent
into rootProjDir
include outputFileName
rename outputFileName , newTargetName
}
println("Copied ${outputFileName} to ${newTargetName}")
}def servicesJSON = file('google-services.json')
if (servicesJSON.file && servicesJSON.text) {
apply plugin: 'com.google.gms.google-services'
} else {
logger.info("google-services.json not found, google-services plugin not applied. Push Notifications won't work")
}class HexagonPainter extends CustomPainter {
final Color color;
HexagonPainter({required this.color});

@override
void paint(Canvas canvas, Size size) {
final path = Path();
final height = size.height;
final width = size.width;

    path.moveTo(size.width / 2, 0);
    path.lineTo(width, height * 0.25);
    path.lineTo(width, height * 0.75);
    path.lineTo(size.width / 2, height);
    path.lineTo(0, height * 0.75);
    path.lineTo(0, height * 0.25);
    path.close();

    final paint = Paint()
      ..color = color
      ..style = PaintingStyle.fill;

    canvas.drawPath(path, paint);
}

@override
bool shouldRepaint(covariant CustomPainter oldDelegate) {
return false;
}
}// For a 64-bit ARM processor
int my_counter __attribute__((aligned(8)));

}
fun someOtherMethod() {
try {
...
} catch (e : SomeException) {
Log.d(TAG, "someOtherMethod()", e)
}
}import android.util.Log
...
class MyActivity : Activity() {
...
override fun onCreate(savedInstanceState: Bundle?) {
...
if (savedInstanceState != null) {
Log.d(TAG, "onCreate() Restoring previous state")
/* restore state */
} else {
Log.d(TAG, "onCreate() No saved state available")
/* initialize app */
}
...
}
...
companion object {
private val TAG: String = MyActivity::class.java.simpleName
...
}
}sysctl kernel.yama.ptrace_scope
run-as your-package-name pwd
fun someOtherMethod() {
try {
...
} catch (e : SomeException) {
Log.d(TAG, "someOtherMethod()", e)
}
}android {
buildTypes {
customDebugType {
debuggable true
...
}
}
}import 'package:flutter/material.dart';
import 'dart:math';

class AlienTechCover {
static Widget generate(String textInput) {
List<String> keywords = textInput.split(' ');

    // Color logic
    Color baseColor = Colors.green;
    if (keywords.contains('blue')) baseColor = Colors.blue;
    if (keywords.contains('red')) baseColor = Colors.red;

    int numLines = keywords.length + 5;

    List<Widget> stackChildren = [
      // Circuit Lines
      for (int i = 0; i < numLines; i++)
        Positioned(
          left: Random().nextDouble() * 300,
          top: Random().nextDouble() * 300,
          child: Container(
            width: Random().nextDouble() * 50 + 10,
            height: 2,
            color: baseColor.shade200.withOpacity(0.5),
          ),
        ),
      // Central Glow
      Center(
        child: Container(
          width: 80,
          height: 80,
          decoration: BoxDecoration(
            color: baseColor.shade400.withOpacity(0.7),
            shape: BoxShape.circle,
            boxShadow: [
              BoxShadow(
                color: baseColor.shade400,
                blurRadius: 20,
                spreadRadius: 5,
              ),
            ],
          ),
        ),
      ),
      // Hexagon Pattern
      for (int i = 0; i < 5; i++)
        Positioned(
          left: Random().nextDouble() * 300,
          top: Random().nextDouble() * 300,
          child: Transform.rotate(
            angle: Random().nextDouble() * pi * 2,
            child: CustomPaint(
              size: Size(20, (20 * 0.8660254037844386)),
              painter: HexagonPainter(color: baseColor.shade300.withOpacity(0.6)),
            ),
          ),
        ),
      // Additional visual: energy pulse if "energy" keyword is present
      if (keywords.contains('energy'))
        Center(
          child: Container(
            width: 120,
            height: 120,
            decoration: BoxDecoration(
              shape: BoxShape.circle,
              gradient: RadialGradient(
                colors: [
                  baseColor.shade100.withOpacity(0.2),
                  baseColor.shade400.withOpacity(0.05),
                  Colors.transparent,
                ],
                stops: [0.5, 0.8, 1.0],
              ),
            ),
          ),
        ),
      // Additional visual: field effect if "field" keyword is present
      if (keywords.contains('field'))
        Positioned.fill(
          child: IgnorePointer(
            child: Container(
              decoration: BoxDecoration(
                gradient: SweepGradient(
                  colors: [
                    baseColor.shade100.withOpacity(0.1),
                    baseColor.shade400.withOpacity(0.15),
                    baseColor.shade100.withOpacity(0.1),
                  ],
                  stops: [0.0, 0.5, 1.0],
                ),
              ),
            ),
          ),
        ),
      // Additional visual: core ring if "core" keyword is present
      if (keywords.contains('core'))
        Center(
          child: Container(
            width: 100,
            height: 100,
            decoration: BoxDecoration(
              shape: BoxShape.circle,
              border: Border.all(
                color: baseColor.shade200.withOpacity(0.5),
                width: 6,
              ),
            ),
          ),
        ),
    ];

    return Container(
      decoration: BoxDecoration(
        color: baseColor.shade900,
      ),
      child: Stack(
        children: stackChildren,
      ),
    );
}
}

class HexagonPainter extends CustomPainter {
final Color color;
HexagonPainter({required this.color});

@override
void paint(Canvas canvas, Size size) {
final path = Path();
final height = size.height;
final width = size.width;

    path.moveTo(size.width / 2, 0);
    path.lineTo(width, height * 0.25);
    path.lineTo(width, height * 0.75);
    path.lineTo(size.width / 2, height);
    path.lineTo(0, height * 0.75);
    path.lineTo(0, height * 0.25);
    path.close();

    final paint = Paint()
      ..color = color
      ..style = PaintingStyle.fill;

    canvas.drawPath(path, paint);
}

@override
bool shouldRepaint(covariant CustomPainter oldDelegate) {
return false;
}
}
<data>
<Number>42</Number>
<Text>hello</Text>
</data>