<script>
  async function GetUserProfile() {
    const response = await fetch("https://randomuser.me/api/") // generazione random dati

    // verifica controllo dati
    if (response.ok) {
      const data = await response.json()
      return data
    } else {
      throw new Error("Errore nella fetch del profilo!!")
    } 
  }
</script>

{#await GetUserProfile()}
  <div>Loading...</div>
{:then profile}
  <pre> <!-- pre, considera l'intestazione -->
    {JSON.stringify(profile, null, 2)}
  </pre>
{:catch error}
  <pre> 
    {JSON.stringify(error, null, 2)}
  </pre>
{/await}