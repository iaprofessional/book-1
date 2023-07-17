<script>
    // imports
    import "../ProactNavbar.svelte";
    import "../AddPageCard.svelte";
    import "bootstrap/dist/css/bootstrap.min.css";
    //import "../Register/style.css";
    import { initializeApp } from 'firebase/app';
    import { collection, getDocs, getFirestore } from 'firebase/firestore';
    import ProactNavbar from "../ProactNavbar.svelte";
    import AddPageCard from "../AddPageCard.svelte";
  
    const firebaseConfig = {
          apiKey: 'AIzaSyCeBCVVfalGWO03XNkJy8F1hJsII6Lgjb0',
          authDomain: 'practice-5c982.firebaseapp.com',
          databaseURL: 'https://practice-5c982-default-rtdb.firebaseio.com',
          projectId: 'practice-5c982',
          storageBucket: 'practice-5c982.appspot.com',
          messagingSenderId: '664592348370',
          appId: '1:664592348370:web:4385f2b327bbc5562aa90b'
      };
      initializeApp(firebaseConfig);
  
    const db = getFirestore();
      const sellerDB = collection(db, 'sellerDB');
  
    // getDocs(sellerDB).then((s) => {
      // 	console.log(s.docs.length);
      // 	console.log(s.docs);
      // });
  
    let data;
   
  </script>
  
  <body class="bg-black">
  <ProactNavbar>
  </ProactNavbar>
    <div class="container">
      <center>
      <br>
      <br>
      <div class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="exampleModalLabel">Enter data</h5>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            <div class="modal-body">
              <AddPageCard>
              </AddPageCard>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
              <button type="button" class="btn btn-primary">Save changes</button>
            </div>
          </div>
        </div>
      </div>
    </center>
    </div>
  </body>  