import streamlit as st
import random

# Set page configuration as the very first Streamlit command
st.set_page_config(page_title="Number Guessing Game", layout="centered")

# Initialize session state variables if not already present
if 'count' not in st.session_state:
    st.session_state['count'] = 0

# Function to increase the count
def count_increase():
    st.session_state['count'] += 1

# Button to increase the count
st.button(label="Click me", on_click=count_increase)

# Display count
st.header(st.session_state['count'])

# Title for the app
st.title("Number Guessing Game")

# Initialize the target number and attempts if not already present
if "target" not in st.session_state:
    st.session_state.target = random.randint(1, 100)
    st.session_state.attempts = 0
    st.session_state.feedback = ""

# Instructions
st.write("I'm thinking of a number between 1 and 100. Try to guess it!")

# Input field for the user's guess
user_guess = st.number_input("Enter your guess:", min_value=1, max_value=100, step=1)

# Button to submit the guess
if st.button("Submit Guess"):
    st.session_state.attempts += 1
    if user_guess < st.session_state.target:
        st.session_state.feedback = "X Too low! Try a higher number."
    elif user_guess > st.session_state.target:
        st.session_state.feedback = "X Too high! Try a lower number."
    else:
        # Correct guess
        st.session_state.feedback = f"Correct! You guessed the number in {st.session_state.attempts} attempts."
        st.balloons()

        # Reset game
        st.session_state.target = random.randint(1, 100)
        st.session_state.attempts = 0

# Display the feedback message
st.write(st.session_state.feedback)





