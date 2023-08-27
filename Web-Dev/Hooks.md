# React
useState(): 



useCallback() : doesn't re-run the function with change in other state, unless certain parameters change, can be used in places of useEffect. We also need to pass dependency parameters.


useEffect(): runs every render but can be controlled using dependencies[], then it will run the functions only when dependencies change, async, will run after everything has run, dont set items in hook, as it might cause infinite loop


useContext(): helps define a data set at an upper level that can be used a provider wrapped to app to drill down the data to components, it provides a context data for the app.


# Redux
useReducer(): 


useDispatch():




useNavigate():

