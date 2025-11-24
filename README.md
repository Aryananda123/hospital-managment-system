# hospital-managment-system
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Hospital Management — Parking & Vehicle Allocator</title>
  <meta name="description" content="Project demo site for a real-time parking slot allocator (HTML + CSS mockup)">
  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --muted:#9aa4b2; --accent:#6ee7b7; --accent-2:#60a5fa;
      --glass: rgba(255,255,255,0.04);
      --max-w:1100px;
      --gap:1.25rem;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{margin:0; background:linear-gradient(180deg,#071025 0%, #071827 100%); color:#e6eef6; -webkit-font-smoothing:antialiased}
    .container{max-width:var(--max-w); margin:36px auto; padding:28px}

    header{display:flex;align-items:center;justify-content:space-between; gap:1rem}
    .brand{display:flex;align-items:center;gap:.8rem}
    .logo{width:48px;height:48px;border-radius:10px;background:linear-gradient(135deg,var(--accent),var(--accent-2));display:flex;align-items:center;justify-content:center;font-weight:700;color:#022;box-shadow:0 6px 18px rgba(6,22,40,.6)}
    h1{font-size:1.25rem;margin:0}
    p.lead{margin:0;color:var(--muted);font-size:.95rem}

    .grid{display:grid;grid-template-columns:1fr 420px;gap:var(--gap);align-items:start;margin-top:20px}
    .card{background:var(--card);border-radius:14px;padding:18px;box-shadow:0 8px 30px rgba(2,6,23,.6);border:1px solid rgba(255,255,255,0.03)}

    /* Project overview */
    .overview h2{margin:.2rem 0 8px;font-size:1.05rem}
    .badges{display:flex;gap:.5rem;flex-wrap:wrap;margin-top:10px}
    .badge{background:var(--glass);padding:.35rem .6rem;border-radius:999px;font-size:.8rem;color:var(--muted)}
    ul.features{margin:12px 0 0;padding-left:18px;color:var(--muted)}

    /* Login mockup */
    .login-roles{display:flex;gap:.6rem;margin:10px 0}
    .role{flex:1;background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);padding:12px;border-radius:10px;text-align:center}
    .role input{display:block;margin:8px auto}
    .login-form{margin-top:12px}
    .field{display:flex;flex-direction:column;margin-bottom:8px}
    input[type=text], input[type=password]{padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:inherit}
    label{font-size:.85rem;color:var(--muted);margin-bottom:6px}
    .btn{display:inline-block;padding:10px 14px;border-radius:10px;background:linear-gradient(90deg,var(--accent),var(--accent-2));color:#022;font-weight:600;border:none;cursor:pointer}

    /* Parking visualizer */
    .parking{display:grid;grid-template-columns:repeat(4,1fr);gap:10px}
    .slot{padding:12px;border-radius:8px;background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);text-align:center;border:1px solid rgba(255,255,255,0.03)}
    .slot .id{font-size:.9rem;color:var(--muted)}
    /* CSS-only availability states via checkbox hack */
    .slot input{display:none}
    .slot label{display:block;padding:10px;border-radius:6px;cursor:pointer}
    .slot input:checked + label{outline:3px solid rgba(102,255,184,0.12)}
    /* status colors */
    .available label{background:linear-gradient(180deg, rgba(102,255,184,0.06), transparent);color:#c8ffe7}
    .occupied label{background:linear-gradient(180deg, rgba(250,100,100,0.04), transparent);color:#ffd6d6}
    .reserved label{background:linear-gradient(180deg, rgba(255,200,80,0.04), transparent);color:#fff6db}

    /* footer */
    footer{margin-top:18px;color:var(--muted);font-size:.9rem;text-align:center}

    /* responsive */
    @media (max-width:960px){.grid{grid-template-columns:1fr}.container{padding:18px}}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">H</div>
        <div>
          <h1>Hospital Management — Parking Allocator</h1>
          <p class="lead">Real-time slot allocation — project demo (May 2023). Built with Java, C++, HTML/CSS (mockup).</p>
        </div>
      </div>
      <div style="text-align:right">
        <div class="badge">May 2023</div>
      </div>
    </header>

    <main class="grid">
      <section class="card overview">
        <h2>Project summary</h2>
        <div class="badges">
          <div class="badge">Languages: Java, C++, HTML, CSS, JS (concept)</div>
          <div class="badge">Features: Role-based login, real-time allocation</div>
          <div class="badge">Focus: Efficient vehicle management</div>
        </div>

        <ul class="features">
          <li>Real-time parking slot allocation for vehicles of different types.</li>
          <li>Secure role-based access (vehicle owner / admin) for controlled workflows.</li>
          <li>Backend-ready design — easy to attach database & APIs.</li>
        </ul>

        <h2 style="margin-top:16px">How to use this mockup</h2>
        <p class="lead" style="margin-top:6px">This single-page demo is built only with HTML & CSS to show the UI and core flows. It does not include a server or database. If you'd like, I can add JavaScript to make it interactive or provide a simple Node/Java backend scaffold.</p>

        <h2 style="margin-top:14px">Project highlights</h2>
        <ul class="features">
          <li>Secure login forms and different role views (visual-only).</li>
          <li>Parking grid demonstrating available / occupied / reserved slots using CSS states.</li>
          <li>Clean, responsive layout suitable for embedding into a portfolio or GitHub Pages.</li>
        </ul>

        <footer>Want backend integration or a downloadable zip? Ask and I'll prepare it.</footer>
      </section>

      <aside class="card">
        <h2 style="margin-top:0">Role-based Login (visual)</h2>
        <div class="login-roles">
          <div class="role">
            <strong>Vehicle Owner</strong>
            <div style="font-size:.85rem;color:var(--muted)">Limited access — request/see allocated slot</div>
          </div>
          <div class="role">
            <strong>Admin</strong>
            <div style="font-size:.85rem;color:var(--muted)">Full access — allocate/manage slots</div>
          </div>
        </div>

        <form class="login-form" onsubmit="return false;">
          <div class="field">
            <label for="username">Username</label>
            <input id="username" type="text" placeholder="owner123" />
          </div>
          <div class="field">
            <label for="password">Password</label>
            <input id="password" type="password" placeholder="••••••" />
          </div>
          <button class="btn">Sign In</button>
        </form>

        <hr style="margin:14px 0;border:none;border-top:1px solid rgba(255,255,255,0.03)" />

        <h2 style="margin-top:0">Parking Visualizer</h2>
        <p style="margin:6px 0;color:var(--muted);font-size:.9rem">Toggle slots to preview states (CSS-only demo).</p>
        <div class="parking" aria-hidden="false">
          <!-- 8 slots as example, more can be added -->

          <div class="slot available">
            <input type="checkbox" id="s1" />
            <label for="s1">
              <div class="id">Slot A1</div>
              <div style="font-size:.8rem">Available</div>
            </label>
          </div>

          <div class="slot occupied">
            <input type="checkbox" id="s2" checked />
            <label for="s2">
              <div class="id">Slot A2</div>
              <div style="font-size:.8rem">Occupied</div>
            </label>
          </div>

          <div class="slot reserved">
            <input type="checkbox" id="s3" />
            <label for="s3">
              <div class="id">Slot A3</div>
              <div style="font-size:.8rem">Reserved</div>
            </label>
          </div>

          <div class="slot available">
            <input type="checkbox" id="s4" />
            <label for="s4">
              <div class="id">Slot B1</div>
              <div style="font-size:.8rem">Available</div>
            </label>
          </div>

          <div class="slot occupied">
            <input type="checkbox" id="s5" checked />
            <label for="s5">
              <div class="id">Slot B2</div>
              <div style="font-size:.8rem">Occupied</div>
            </label>
          </div>

          <div class="slot available">
            <input type="checkbox" id="s6" />
            <label for="s6">
              <div class="id">Slot B3</div>
              <div style="font-size:.8rem">Available</div>
            </label>
          </div>

          <div class="slot reserved">
            <input type="checkbox" id="s7" />
            <label for="s7">
              <div class="id">Slot C1</div>
              <div style="font-size:.8rem">Reserved</div>
            </label>
          </div>

          <div class="slot available">
            <input type="checkbox" id="s8" />
            <label for="s8">
              <div class="id">Slot C2</div>
              <div style="font-size:.8rem">Available</div>
            </label>
          </div>

        </div>

        <p style="margin-top:12px;color:var(--muted);font-size:.85rem">Note: To make this functional, we can connect the UI to a backend (Java REST API or Node) that returns slot states and accepts allocation requests.</p>
      </aside>
    </main>

  </div>
</body>
</html>
