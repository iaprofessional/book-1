<script>
  // imports
  import "../ProactNavbar.svelte";
  import "../ProactCard.svelte";
  import "bootstrap/dist/css/bootstrap.min.css";
  //import "../Register/style.css";
  import { initializeApp } from 'firebase/app';
	import { collection, getDocs, getFirestore } from 'firebase/firestore';
    import ProactNavbar from "../ProactNavbar.svelte";
    import ProactCard from "../ProactCard.svelte";

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
    <div id="books-container" class="row mt-5">
      {#await getDocs(sellerDB) then s}
        {#each s.docs as data}
        <ProactCard image={data["_document"]["data"]["value"]["mapValue"]["fields"]["image"].stringValue} title={data.id} subtitle={data["_document"]["data"]["value"]["mapValue"]["fields"]["number"].stringValue} text={data["_document"]["data"]["value"]["mapValue"]["fields"]["price"].stringValue}>
        </ProactCard>
        {/each}
        {/await}
    </div>
  </div>
</body>
