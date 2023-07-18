<script>
    // import "bootstrap/dist/js/bootstrap.bundle.min.js";
    //import "../AddPageCard.svelte";
    import "bootstrap/dist/css/bootstrap.min.css";
    import "./style.css";
    import "../ProactNavbar.svelte";
    import { initializeApp } from "firebase/app";
    import { collection, getDocs, getFirestore } from "firebase/firestore";
    import ProactNavbar from "../ProactNavbar.svelte";
  
    const firebaseConfig = {
      apiKey: "AIzaSyCeBCVVfalGWO03XNkJy8F1hJsII6Lgjb0",
      authDomain: "practice-5c982.firebaseapp.com",
      databaseURL: "https://practice-5c982-default-rtdb.firebaseio.com",
      projectId: "practice-5c982",
      storageBucket: "practice-5c982.appspot.com",
      messagingSenderId: "664592348370",
      appId: "1:664592348370:web:4385f2b327bbc5562aa90b",
    };
  
    initializeApp(firebaseConfig);
  
    const db = getFirestore();
    const buyerDB = collection(db, "buyerDB");
  
    getDocs(buyerDB).then((s) => {
      // console.log(s.docs.length);
      // console.log(s.docs);
    });
    const data = [
      {
        name: "sample",
        title: "Item 1",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 2",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 3",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 4",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 5",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 6",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 7",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 8",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 9",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 10",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 11",
        number: "+91 12345 67890",
      },
      {
        name: "sample",
        title: "Item 12",
        number: "+91 12345 67890",
      },
    ];
  </script>
  
  <body class="bg-black">
<ProactNavbar></ProactNavbar>
    <div class="container mt-5">
      <div class="row mt-5">
        {#each data as i}
          <div class="col-md-3 mt-4">
            <div class="box">
              <h1>{i.title}</h1>
              <br />
              <h3>{i.name}</h3>
              <br />
              <h3>{i.number}</h3>
            </div>
          </div>
        {/each}
      </div>
    </div></body
  >
  