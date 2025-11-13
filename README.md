<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Rainbow Gradient Text + Images</title>
  <style>
    /* Make the whole page black */
    html, body {
      height: 100%;
      margin: 0;
      background: #000; /* solid black background */
      color: #fff;
      font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    /* Center content */
    .wrap {
      min-height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 1rem;
      padding: 2rem;
      box-sizing: border-box;
      text-align: center;
    }

    /* Rainbow text that moves as a gradient */
    .rainbow {
      font-size: clamp(2.25rem, 8vmin, 6rem);
      font-weight: 800;
      line-height: 1;
      /* gradient colors */
      background: linear-gradient(
        90deg,
        #ff0000,
        #ff7a00,
        #ffff00,
        #00ff00,
        #00ffff,
        #0000ff,
        #8b00ff,
        #ff007f,
        #ff0000
      );
      background-size: 200% 100%; /* make gradient wider so it can move */
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent; /* fallback */
      -webkit-text-fill-color: transparent; /* Safari */
      animation: gradient-move 6s linear infinite;
      margin: 0;
      padding: 0 1rem;
      text-wrap: balance;
    }

    @keyframes gradient-move {
      0%   { background-position: 0% 50%; }
      100% { background-position: 200% 50%; }
    }

    /* Optional subtle glow */
    .rainbow {
      filter: drop-shadow(0 6px 20px rgba(0,0,0,0.8));
    }

    /* Simple responsive image gallery */
    .gallery {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
    }

    .gallery img {
      max-width: min(45vw, 320px);
      width: 100%;
      height: auto;
      border-radius: 8px;
      border: 3px solid rgba(255,255,255,0.06);
      box-shadow: 0 10px 30px rgba(0,0,0,0.6);
    }

    /* small helper text */
    .hint { color: #bfbfbf; font-size: .95rem; }
    a.example-link { color: #9fd6ff; text-decoration: underline; }
  </style>
</head>
<body>
  <div class="wrap">
    <h1 class="rainbow">welcome to my page</h1>
    <p class="hint">click the prize.</p>

    <div class="gallery" aria-label="Example images">
      <!-- Local image (put the file at repo/images/photo1.jpg) -->
      <img src="[images/photo1.jpg](https://i.redd.it/te6pkxxjck561.png)" alt="Example photo from repo">

      <!-- Remote image example (not recommended for production unless stable URL) -->
      <img src="https://raw.githubusercontent.com/<owner>/<repo>/main/images/photo2.jpg" alt="Example remote photo">
    </div>

    <p class="hint">Make an image clickable: <a class="example-link" href="https://example.com" target="_blank" rel="noopener noreferrer">clickable image link</a></p>
  </div>
</body>
</html>


  [the prize!](https://www.desmos.com/calculator/e63zhdudbg)

