copy each time
const firebaseConfig = {
  apiKey:            "AIzaSyCFUSS1lqhPvIuNXk5hVjdRp47RqiAOpmA",
  authDomain:        "york-actor-network.firebaseapp.com",
  projectId:         "york-actor-network",
  storageBucket:     "york-actor-network.firebasestorage.app",
  messagingSenderId: "572469498607",
  appId:             "1:572469498607:web:9744a540f2ea78d7d7011a"
};

const fbApp = initializeApp(firebaseConfig);
const auth  = getAuth(fbApp);
const db    = getFirestore(fbApp);
const googleProvider = new GoogleAuthProvider();

/* ┌────────────────────────────────────────────────────────────────┐
   │  OPTIONAL: organiser email notifications via EmailJS.            │
   │  Fill these from your EmailJS dashboard (see FIREBASE_SETUP.md). │
   │  Leave any field blank to disable email entirely — sign-ups      │
   │  still work without it. These IDs are public by design.          │
   └────────────────────────────────────────────────────────────────┘ */
const EMAILJS = {
  publicKey:  "HDmnKCrZGvd8uC-DD",   // EmailJS "Public Key"
  serviceId:  "service_yvta7ki",   // EmailJS Service ID  (e.g. service_xxxxxxx)
  templateId: "template_26yta3g"    // EmailJS Template ID (e.g. template_xxxxxxx)
};
