// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: "AIzaSyCtcrNl6Y20Zf6fj3QpIYR23kpf2jwBroQ",
  authDomain: "transformadoresapp-24b7d.firebaseapp.com",
  projectId: "transformadoresapp-24b7d",
  storageBucket: "transformadoresapp-24b7d.firebasestorage.app",
  messagingSenderId: "63578086453",
  appId: "1:63578086453:web:396a2ccbfa9de6d5ea657c",
  measurementId: "G-LR4NR6PECG"
};

// Inicializar Firebase
const app = firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();

// Referencia a la lista en la interfaz
const lista = document.getElementById("lista");

// Función: agregar nuevo transformador
function nuevoTransformador() {
const nombre = prompt("Nombre del transformador:");
if (nombre) {
db.collection("transformadores").add({
nombre: nombre,
fecha: new Date().toISOString()
});
}
}

// Escuchar en tiempo real la colección de transformadores
db.collection("transformadores").orderBy("fecha", "desc")
.onSnapshot(snapshot => {
lista.innerHTML = "";
snapshot.forEach(doc => {
const data = doc.data();
const li = document.createElement("li");
li.textContent = data.nombre;
lista.appendChild(li);
});
});
