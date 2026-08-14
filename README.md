# College-portal-<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/12.17.1/firebase-app.js";
  import { getDatabase, ref, set, get } from "https://www.gstatic.com/firebasejs/12.17.1/firebase-database.js";

  const firebaseConfig = {
    apiKey: "AIzaSyDeyRHGcP5BSyVZDfuW0LmyCoDvZh8cJLo",
    authDomain: "college-portal-aryan.firebaseapp.com",
    databaseURL: "https://college-portal-aryan-default-rtdb.firebaseio.com/",
    projectId: "college-portal-aryan",
    storageBucket: "college-portal-aryan.firebasestorage.app",
    messagingSenderId: "746430590245",
    appId: "1:746430590245:web:c3e9fb782f55ebafd97ecc"
  };

  const app = initializeApp(firebaseConfig);
  const db = getDatabase(app);

  // Example: Student data save
  window.saveStudentToFirebase = async function(studentId, studentData) {
    await set(ref(db, "students/" + studentId), studentData);
    console.log("Student saved successfully");
  };

  // Example: Student data read
  window.getStudentsFromFirebase = async function() {
    const snapshot = await get(ref(db, "students"));
    return snapshot.exists() ? snapshot.val() : {};
  };
</script>
