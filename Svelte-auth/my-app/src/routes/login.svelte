<script>

    import {goto} from "@sapper/app.mjs"
  let email = "",
    password = "";

    const submit = async ()=>{
        await fetch('http://localhost:8000/api/login',{
            method: 'POST',
            headers: {'Content-Type':'application/json'},
            credentials:'include',
            body: JSON.stringify({
                email,password
            })
        });

        await goto('/')
    }
</script>

<form on:submit|preventDefault={submit}>
  
    <h1 class="h3 mb-3 fw-normal">Please sign in</h1>
  
      <input
        type="email"
        class="form-control"
        id="floatingInput"
        placeholder="name@example.com"
        bind:value={email}
        required
      />
      <input
        type="password"
        class="form-control"
        id="floatingPassword"
        placeholder="Password"
        bind:value={password}
        required
      />
     
  
      <label>
        <input type="checkbox" value="remember-me" /> Remember me
      </label>
    <button class="w-100 btn btn-lg btn-primary" type="submit">Sign in</button>
  </form>
  