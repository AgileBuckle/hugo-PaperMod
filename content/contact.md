title: "Contact"
date: 2024-12-07
layout: "contact"  # Ensure you have a custom layout or default layout to render this page
---

<h2>Contact Us</h2>

<p>Please fill out the form below to reach out to us. We look forward to hearing from you!</p>

<form id="contact-form">
  <div>
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required />
  </div>

  <div>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required />
  </div>

  <div>
    <label for="message">Message:</label>
    <textarea id="message" name="message" required></textarea>
  </div>

  <div>
    <button type="submit">Send</button>
  </div>
</form>

<!-- Success message (hidden by default) -->
<p id="success-message" style="display: none;">Thank you for your message! We will get back to you shortly.</p>

<!-- Error message (hidden by default) -->
<p id="error-message" style="display: none; color: red;">There was an error submitting the form. Please try again later.</p>

<script>
document.getElementById("contact-form").addEventListener("submit", function(event) {
  event.preventDefault(); // Prevent default form submission

  // Get form data
  const name = document.getElementById("name").value;
  const email = document.getElementById("email").value;
  const message = document.getElementById("message").value;

  // Construct mailto link
  const subject = encodeURIComponent(`Contact form submission from ${name}`);
  const body = encodeURIComponent(`Name: ${name}\nEmail: ${email}\nMessage: ${message}`);

  // Construct the mailto URL
  const mailtoLink = `mailto:contact@agilebuckle.com?subject=${subject}&body=${body}`;

  // Try to redirect to mailto link
  try {
    window.location.href = mailtoLink;
    // Show success message
    document.getElementById("success-message").style.display = "block";
  } catch (error) {
    // Show error message
    document.getElementById("error-message").style.display = "block";
  }
});
</script>

<style>
#contact-form {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f9f9f9;
}

#contact-form div {
  margin-bottom: 15px;
}

#contact-form label {
  display: block;
  font-weight: bold;
}

#contact-form input,
#contact-form textarea {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

#contact-form button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 15px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

#contact-form button:hover {
  background-color: #45a049;
}

#success-message {
  color: green;
}

#error-message {
  color: red;
}
</style>