# login-script
login script using html

<html>

<body>
  <form>
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    Date of brith:<input type="date" id="dob" required>
    <div id="age-range">
      Age: <input type="range" id="age" min="18" max="100"></div>
    <div id="email-group">
      Email:<input type="email" id="email" required></div>
    <div id="website-group">
      Website:<input type="url" id="website"></div>
    <button type="submit">Sign up</button>
  </form>

  <script>
    const ageRange = document.getElementById("age-range");
    const emailGroup = document.getElementById("email-group");
    const websiteGroup = document.getElementById("website-group");
    ageRange.style.display = "none";
    emailGroup.style.display = "none";
    websiteGroup.style.display = "none";
    document.getElementById("dob").addEventListener("change", function () {
      const age = calculateAge(this.value);
      if (age < 18) {
        ageRange.style.display = "none";
        emailGroup.style.display = "none";
        websiteGroup.style.display = "none";
      }
      else if (age >= 18 && age <= 25) {
        ageRange.style.display = "block";
        emailGroup.style.dispaly = "block";
        websiteGroup.style.display = "none";
      }
      else {
        ageRange.style.display = "block";
        emailGroup.style.display = "block";
        websiteGroup.style.display = "block";
      }
    });
    function calculateAge(brithday) {
      const today = new Date();
      const brithDate = new Date(birthday);
      let age = today.getFullYear() - birthDate.getFullYear();
      return age;
    }
  </script>

</body>

</html>
