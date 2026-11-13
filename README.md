# Ex.-6-React-Lab-Exercise-Form-Validation
## Name: Madhan Kumar J
## Roll no: 2305001016
## Department: CSE

## AIM
### To create a React form with validation for required fields, email, and password, and to display appropriate error messages for invalid inputs.

## PROGRAM
### i) App.jsx
```py
import { useState } from "react";
import "./App.css";
function App() {
 const [formData, setFormData] = useState({
 name: "",
 email: "",
 password: "",
 });
 const [errors, setErrors] = useState({});
 const handleChange = (e) => {
 setFormData({
 ...formData,
 [e.target.name]: e.target.value,
 });
 };
 const validate = () => {
 let newErrors = {};
 if (formData.name.trim() === "") {
 newErrors.name = "Name is required";
 }
 if (formData.email.trim() === "") {
 newErrors.email = "Email is required";
 } else if (!formData.email.includes("@")) {
 newErrors.email = "Enter a valid email";
 }
 if (formData.password === "") {
 newErrors.password = "Password is required";
 } else if (formData.password.length < 6) {
 newErrors.password =
 "Password must contain at least 6 characters";
 }
 return newErrors;
 };
 const handleSubmit = (e) => {
 e.preventDefault();
 const validationErrors = validate();
 setErrors(validationErrors);
 if (Object.keys(validationErrors).length === 0) {
 alert("Form submitted successfully!");
 }
 };
 return (
 <div className="container">
 <h1>Registration Form</h1>
 <form onSubmit={handleSubmit}>
 <label>Name:</label>
 <input
 type="text"
 name="name"
 value={formData.name}
 onChange={handleChange}
 placeholder="Enter your name"
 />
 {errors.name && <p>{errors.name}</p>}
 <label>Email:</label>
 <input
 type="text"
 name="email"
 value={formData.email}
 onChange={handleChange}
 placeholder="Enter your email"
 />
 {errors.email && <p>{errors.email}</p>}
 <label>Password:</label>
 <input
 type="password"
 name="password"
 value={formData.password}
 onChange={handleChange}
 placeholder="Enter your password"
 />
 {errors.password && <p>{errors.password}</p>}
 <button type="submit">Register</button>
 </form>
 </div>
 );
}
export default App;
```
### ii) App.css
```py
. container {
 width: 350px;
 margin: 50px auto;
 padding: 25px;
 border: 1px solid gray;
 border-radius: 10px;
}
h1 {
 text-align: center;
}
form {
 width: 100%;
}
label {
 display: block;
 margin-top: 15px;
 font-weight: bold;
}
input {
 width: 100%;
 padding: 8px;
 margin-top: 5px;
 box-sizing: border-box;
}
p {
 color: red;
 margin: 5px 0;
}
button {
 margin-top: 20px;
 padding: 10px 20px;
 cursor: pointer;
}
```
## OUTPUT
<img width="796" height="488" alt="image" src="https://github.com/user-attachments/assets/8c9b49b5-ea39-47c5-83e5-69deba3fa063" />
<img width="833" height="562" alt="image" src="https://github.com/user-attachments/assets/c31802d7-8c45-413d-bd81-da68fe525f33" />



## RESULT
### Thus, the React form validation was successfully implemented using useState(), onChange, and onSubmit. The application successfully validated required fields, email format, and password length, and displayed appropriate error messages for invalid inputs.
