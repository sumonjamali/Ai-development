# Ai-development
Development commit
import openai

# Initialize OpenAI API
openai.api_key = "your_api_key_here"

def generate_show_script(prompt):
    """Generates a script based on the given prompt."""
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[
            {"role": "system", "content": "You are a creative scriptwriter for shows."},
            {"role": "user", "content": prompt}
        ],
        max_tokens=500,
        temperature=0.7
    )
    return response.choices[0].message['content']

# Example prompt for generating a script
prompt = """
Write a short scene for a comedy show where two roommates argue about a robot they accidentally ordered online.
"""

# Generate the script
script = generate_show_script(prompt)
print(script)
