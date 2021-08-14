<script>

    import {goto} from "@sapper/app.mjs"
  let name = "",
    email = "",
    password = "";

    const submit = async ()=>{
        await fetch('http://localhost:8000/api/register',{
            method: 'POST',
            headers: {'Content-Type':'application/json'},
            body: JSON.stringify({
                name,email,password
            })
        });

        await goto('/login')
    }
</script>

<form on:submit|preventDefault={submit}>
  <h1 class="h3 mb-3 fw-normal">Please register</h1>

  <input type="text" class="form-control" placeholder="Name" required bind:value={name} />
  <input
    type="email"
    class="form-control"
    placeholder="Email address"
    required
    bind:value={email}
  />
  <input type="password" class="form-control" placeholder="Password" required bind:value={password} />

  <button class="w-100 btn btn-lg btn-primary" type="submit">Register</button>
</form>
