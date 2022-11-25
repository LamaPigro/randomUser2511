<script>
  async function GetUserProfile() {
    const response = await fetch("https://randomuser.me/api/")

    // verifica controllo dati
    if (response.ok) {
      const data = await response.json()
      return data
    } else {
      throw new Error("Errore nella fetch del profilo!!")
    } 
  }
</script>

<main>
  
</main>

<style>
  
</style>
