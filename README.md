import streamlit as st

# Initialize session state for navigation
if "page" not in st.session_state:
    st.session_state.page = "login"

# Navigation function
def navigate_to(page):
    st.session_state.page = page

# Login Page
if st.session_state.page == "login":
    st.title("Welcome to CuraPath")
    st.write("Empowering lives, bridging health gaps.")
    
    username = st.text_input("Username")
    password = st.text_input("Password", type="password")
    
    if st.button("Login"):
        navigate_to("user_type")
    
    st.write("Don't have an account? [Sign up here](#)")

# User Type Selection Page
elif st.session_state.page == "user_type":
    st.title("Choose Your Interface")
    if st.button("PWD (Persons with Disabilities)"):
        navigate_to("introduction_pwd")
    if st.button("Commoner"):
        navigate_to("introduction_commoner")

# Introduction Page for PWD
elif st.session_state.page == "introduction_pwd":
    st.title("About CuraPath")
    st.write(
        "This app focuses on the mental and physical health of persons with disabilities (PWDs), "
        "providing tailored benefits like therapy sessions and personalized treatment kits."
    )
    if st.button("Next"):
        navigate_to("features_pwd")

# Introduction Page for Commoners
elif st.session_state.page == "introduction_commoner":
    st.title("About CuraPath")
    st.write(
        "This app focuses on fostering inclusivity and understanding while providing insights into "
        "the needs of persons with disabilities (PWDs)."
    )
    if st.button("Next"):
        navigate_to("features_commoner")

# Features Page for PWD
elif st.session_state.page == "features_pwd":
    st.title("Explore CuraPath Features")
    st.write("1. *Quiz*: Gain insights into your specific issues.")
    st.write("2. *Therapist Connect*: Easily schedule therapy sessions.")
    st.write("3. *Personalized Kits*: Tailored treatment packages.")
    if st.button("Get Started"):
        st.write("Feature implementation coming soon!")

# Features Page for Commoners
elif st.session_state.page == "features_commoner":
    st.title("Explore CuraPath Features")
    st.write("1. *Awareness Programs*: Foster inclusivity and understanding.")
    st.write("2. *Therapist Connect*: Resources to support PWDs.")
    st.write("3. *Educational Resources*: Learn more about PWDs' needs.")
    if st.button("Get Started"):
        st.write("Feature implementation coming soon!")
