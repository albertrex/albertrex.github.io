---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
---

![COVER]({{ site.baseurl }}assets/COVER2.jpg)

<form id="signup" action="https://formspree.io/f/xyewzner" method="POST" class="signup">
  <label for="signup-email">Get notified of new posts</label>
  <div class="signup-row">
    <input type="email" id="signup-email" name="email" placeholder="you@example.com" required>
    <button type="submit">Sign up</button>
  </div>
  <input type="text" name="_gotcha" tabindex="-1" autocomplete="off" style="display:none">
  <p id="signup-status" role="status"></p>
</form>
<style>
  .signup { margin: 2rem 0; max-width: 28rem; }
  .signup label { display: block; margin-bottom: .5rem; }
  .signup-row { display: flex; gap: .5rem; }
  .signup input[type="email"] { flex: 1; padding: .5rem; border: 1px solid #ccc; border-radius: 3px; font: inherit; }
  .signup button { padding: .5rem 1rem; border: 0; border-radius: 3px; background: #2a7ae2; color: #fff; font: inherit; cursor: pointer; }
</style>
<script>
  document.getElementById('signup').addEventListener('submit', async function (e) {
    e.preventDefault();
    var status = document.getElementById('signup-status');
    try {
      var res = await fetch(this.action, { method: 'POST', body: new FormData(this), headers: { 'Accept': 'application/json' } });
      if (res.ok) { status.textContent = 'Thanks, you’re on the list.'; this.reset(); }
      else { status.textContent = 'Something went wrong. Try again.'; }
    } catch (err) { status.textContent = 'Network error. Try again.'; }
  });
</script>

