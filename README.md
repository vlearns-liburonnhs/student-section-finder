<body>
  <!-- Liburon NHS Logo -->
  <div style="text-align: center;">
    <img src="liburon-logo.png" alt="Liburon NHS Logo" width="100" />
    <h2>Student Section Finder</h2>
  </div>

  <input type="text" id="searchInput" placeholder="Enter your full name..." />
  <div id="result"></div>

  <script>
    const students = [
      { name: "Baculpo John Mike", section: "Grade 11 - Socrates", adviser: "Mr. Clemente A. Villacastin, Jr.", adviserPhoto: "mr-villacastin.jpg" },
      { name: "Almonte Kevin James", section: "Grade 11 - Aristotle", adviser: "Mr. Phil Jay M. Duangon", adviserPhoto: "mr-duangon.jpg" },
      // Add more students...
    ];

    document.getElementById("searchInput").addEventListener("input", function () {
      const query = this.value.trim().toLowerCase();
      const resultDiv = document.getElementById("result");

      if (!query) {
        resultDiv.innerHTML = "";
        return;
      }

      const student = students.find(s => s.name.toLowerCase() === query);

      if (student) {
        resultDiv.innerHTML = `
          <strong>Student Name:</strong> ${student.name}<br>
          <strong>Section:</strong> ${student.section}<br>
          <strong>Class Adviser:</strong> ${student.adviser}<br><br>
          <img src="${student.adviserPhoto}" alt="${student.adviser}" width="150" style="border-radius: 8px;" />
        `;
      } else {
        resultDiv.innerHTML = `No record found for "${this.value}". Please check the spelling.`;
      }
    });
  </script>
</body>
