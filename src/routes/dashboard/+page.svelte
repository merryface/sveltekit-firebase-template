<script>
  import {authHandlers, authStore} from '$lib/store/store'
  import {db} from '$lib/firebase/firebase.js'
  import { doc, getDoc, setDoc } from "firebase/firestore";
  let dataArray = []
  let currentItem = ''
  let error = false

  authStore.subscribe(curr => {
    dataArray = curr.data.dbDataArray
  })

  const addToDo = () => {
    error = false
    if (!currentItem) error = true
    if (currentItem) {
      dataArray = [...dataArray, currentItem]
      currentItem = ''
    }
  }

  const editItem = index => {
    let newdataArray = dataArray.filter((todo, i) => i !== index)
    currentItem = dataArray[index]
    dataArray = newdataArray
  }

  const deleteItem = index => {
    let newdataArray = dataArray.filter((todo, i) => i !== index)
    dataArray = newdataArray
}

async function saveDbDataArray() {
  console.log("Saving dbDataArray")
  try {
    const userRef = doc(db, "users", $authStore.user.uid);
    await setDoc(
      userRef,
      {
        dbDataArray: dataArray,
      },
      { merge: true }
    );
  } catch (err) {
  console.log("There was an error saving your information", err);
  }
  }
</script>

{#if !$authStore.loading}
  <div class="mainContainer">      
    <main>
    </main>
  </div>
{/if}

<style>
</style>