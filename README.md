import streamlit as st
if 'count' not in st.session_state:
 st.session_state['count']=0
def count_increase():
st.session_state['count']+=1
st.button(label="click me",on_click=count_i
st.header(st.session_state['count'])
st.set_page_config(page_title Humber Guessing Game", layout centered")
st.title(nber Guessing Game")
if "target" not in st.session_state:
st.session state.target-random.randint(1,100)
st.session state.attempts-0
st.session_state.feedback"
st.write("I'm thinking of a number number between 1 and 100. Try to guess it!")user guess-st.number input("Enter your guess:",min_value-1,max_value-100, step-1)
if st.button("Submit Guess"):
st.session_state.feedback="X Too low! Try a higher number."
elif user guess>st.session state.target:
st.session state.attempts+-1
if user guesscst.session_state.target:
st.session_state.feedback="X Too high! Try a lower number."
else:
st.session_state.feedback=f"Correct! You guessed the number in (st.session state.attempts) attempts."
st.balloons()
st.session state.target-random.randint(1,100)
st.session_state.attempts-
st.write(st.session_state.feedback)



