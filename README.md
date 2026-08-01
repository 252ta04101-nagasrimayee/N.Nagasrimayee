import streamlit as st
st.set_page_config(page_title="Ohm's Law Calculator", layout="centered")
st.title("⚡ Ohm’s Law Calculator")
st.write("Use this calculator to find Voltage (V), Current (I), or Resistance (R)")
# User selection
option = st.selectbox(
    "What do you want to calculate?",
    ("Voltage (V)", "Current (I)", "Resistance (R)")
)
# Input fields based on selection
if option == "Voltage (V)":
    current = st.number_input("Enter Current (I) in Amperes", min_value=0.0)
    resistance = st.number_input("Enter Resistance (R) in Ohms", min_value=0.0)    
    if st.button("Calculate Voltage"):
        voltage = current * resistance
        st.success(f"Voltage (V) = {voltage:.2f} Volts")
elif option == "Current (I)":
    voltage = st.number_input("Enter Voltage (V) in Volts", min_value=0.0)
    resistance = st.number_input("Enter Resistance (R) in Ohms", min_value=0.1)    
    if st.button("Calculate Current"):
        current = voltage / resistance
        st.success(f"Current (I) = {current:.2f} Amperes")
elif option == "Resistance (R)":
    voltage = st.number_input("Enter Voltage (V) in Volts", min_value=0.0)
    current = st.number_input("Enter Current (I) in Amperes", min_value=0.1) 
    if st.button("Calculate Resistance"):
        resistance = voltage / current
        st.success(f"Resistance (R) = {resistance:.2f} Ohms")
st.markdown("---")
st.caption("Formula: V = I × R")
