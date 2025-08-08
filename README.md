<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bookvia - Free eBooks & Services</title>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet" />
  <style>
    body { margin: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: url('https://images.unsplash.com/photo-1512820790803-83ca734da794?auto=format&fit=crop&w=1950&q=80') no-repeat center center fixed; background-size: cover; color: #fff; }
    body::before { content: ""; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.6); z-index: -1; }
    header { background: rgba(0, 0, 0, 0.8); padding: 20px; text-align: center; }
    header h1 { margin: 0; font-size: 2.5em; color: #ffdd57; }
    nav { background: rgba(0, 0, 0, 0.6); display: flex; justify-content: center; gap: 15px; padding: 10px; flex-wrap: wrap; }
    nav a { color: #fff; text-decoration: none; font-weight: bold; }
    .section-title { text-align: center; font-size: 2em; margin: 40px 0 10px; color: #ffdd57; }
    .books { display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)); gap: 20px; padding: 20px; max-width: 1200px; margin: auto; }
    .book { background: rgba(255, 255, 255, 0.1); padding: 15px; border-radius: 10px; text-align: center; display: flex; flex-direction: column; align-items: center; }
    .book img { width: 100%; max-width: 180px; height: 270px; object-fit: cover; border-radius: 5px; }
    .book h3 { margin-top: 10px; }
    .book a { display: inline-block; margin-top: 10px; padding: 10px 15px; background: #ffdd57; color: #000; text-decoration: none; border-radius: 5px; width: 100%; max-width: 140px; text-align: center; box-sizing: border-box; }
    .pagination { text-align: center; margin-top: 20px; }
    .pagination button { padding: 10px 20px; background: #ffdd57; border: none; border-radius: 5px; font-weight: bold; cursor: pointer; margin: 0 5px; }
    .footer { text-align: center; padding: 30px 10px; background: rgba(0, 0, 0, 0.8); color: #ccc; }
    .social-icons i, .cert-logos img { margin: 0 10px; font-size: 1.5em; vertical-align: middle; }
    .cert-logos img { height: 50px; margin-top: 10px; }
    #contact form { display: flex; flex-direction: column; max-width: 500px; margin: 30px auto; }
    #contact input, #contact textarea { padding: 10px; margin-bottom: 15px; border: none; border-radius: 5px; font-size: 1em; }
    #contact button { background-color: #ffdd57; color: #000; padding: 10px; border: none; border-radius: 5px; font-weight: bold; cursor: pointer; font-size: 1em; }
    .thank-you { text-align: center; color: #0f0; font-size: 1.2em; margin-top: 10px; }
  </style>
</head>
<body>

  <header>
    <h1>Bookvia - Free Digital eBooks & Services</h1>
  </header>

  <nav>
    <a href="#">Home</a>
    <a href="#services">Services</a>
    <a href="#books">eBooks</a>
    <a href="#contact">Contact</a>
  </nav>

  <h2 class="section-title" id="books">Free eBooks</h2>
  <section class="books" id="bookGrid"></section>
  <div class="pagination">
    <button onclick="prevBookPage()">Previous</button>
    <button onclick="nextBookPage()">Next</button>
  </div>

  <h2 class="section-title" id="services">Our Free Services</h2>
  <section class="books">
    <div class="book"><h3>PDF Editor</h3><a href="https://www.ilovepdf.com/" target="_blank" rel="noopener">Use Tool</a></div>
    <div class="book"><h3>Image Compressor</h3><a href="https://tinypng.com/" target="_blank" rel="noopener">Use Tool</a></div>
    <div class="book"><h3>Text to Speech</h3><a href="https://ttsmp3.com/" target="_blank" rel="noopener">Use Tool</a></div>
  </section>

  <h2 class="section-title" id="contact">Contact Us</h2>
  <section id="contact">
    <form action="https://formspree.io/f/mdkdppol" method="POST" onsubmit="showThankYou(event)">
      <input type="text" name="name" placeholder="Your Name" required />
      <input type="email" name="email" placeholder="Your Email" required />
      <textarea name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <div class="thank-you" id="thankYou" style="display:none;">Thank you! Your message has been sent.</div>
  </section>

  <footer class="footer">
    <div class="social-icons">
      <a href="#" aria-label="Facebook"><i class="fab fa-facebook"></i></a>
      <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
      <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
      <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
    </div>
    <div class="cert-logos">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/59/ISO_9001-2015.svg/512px-ISO_9001-2015.svg.png" alt="ISO 9001" />
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/ISO_27001.svg/512px-ISO_27001.svg.png" alt="ISO 27001" />
    </div>
    <p style="margin-top: 20px; max-width: 700px; margin-left: auto; margin-right: auto;">
      Bookvia is your one-stop destination for free eBooks and powerful online services. We provide quality digital content and tools to empower your learning and productivity journey.
    </p>
  </footer>

  <script>
    const booksPage1 = [
      { title: "Think and Grow Rich", img: "https://covers.openlibrary.org/b/id/11110465-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Alchemist", img: "https://covers.openlibrary.org/b/id/8231996-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Atomic Habits", img: "https://covers.openlibrary.org/b/id/10385865-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Deep Work", img: "https://covers.openlibrary.org/b/id/11109469-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Rich Dad Poor Dad", img: "https://covers.openlibrary.org/b/id/11110224-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" }
    ];

    const booksPage2 = [
      { title: "1984", img: "https://covers.openlibrary.org/b/id/153541-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "To Kill a Mockingbird", img: "https://covers.openlibrary.org/b/id/8228691-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Great Gatsby", img: "https://covers.openlibrary.org/b/id/7222246-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Moby-Dick", img: "https://covers.openlibrary.org/b/id/5550756-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Pride and Prejudice", img: "https://covers.openlibrary.org/b/id/8281996-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "War and Peace", img: "https://covers.openlibrary.org/b/id/6982161-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Catcher in the Rye", img: "https://covers.openlibrary.org/b/id/8231856-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Crime and Punishment", img: "https://covers.openlibrary.org/b/id/8146542-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Odyssey", img: "https://covers.openlibrary.org/b/id/6979861-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Brave New World", img: "https://covers.openlibrary.org/b/id/8774252-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Jane Eyre", img: "https://covers.openlibrary.org/b/id/8232266-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Wuthering Heights", img: "https://covers.openlibrary.org/b/id/8232281-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Hobbit", img: "https://covers.openlibrary.org/b/id/6979781-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Fahrenheit 451", img: "https://covers.openlibrary.org/b/id/9257752-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Picture of Dorian Gray", img: "https://covers.openlibrary.org/b/id/8306669-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Les Misérables", img: "https://covers.openlibrary.org/b/id/8232268-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Dracula", img: "https://covers.openlibrary.org/b/id/6982046-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Frankenstein", img: "https://covers.openlibrary.org/b id/8232199-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "The Count of Monte Cristo", img: "https://covers.openlibrary.org/b id/8232306-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" },
      { title: "Great Expectations", img: "https://covers.openlibrary.org/b id/8232255-L.jpg", link: "https://www.profitableratecpm.com/y34heuih?key=68d160b89c8a42f4f15cc1999828b0e5" }
    ];

    let currentPage = 0;

    function renderBooks() {
      const bookGrid = document.getElementById("bookGrid");
      bookGrid.innerHTML = "";
      const booksToShow = currentPage === 0 ? booksPage1 : booksPage2;
      booksToShow.forEach(book => {
        const div = document.createElement("div");
        div.className = "book";
        div.innerHTML = `
          <img src="${book.img}" alt="${book.title}" />
          <h3>${book.title}</h3>
          <a href="${book.link}" target="_blank" rel="noopener">Download</a>
        `;
        bookGrid.appendChild(div);
      });
    }

    function nextBookPage() {
      currentPage = currentPage === 0 ? 1 : 0;
      renderBooks();
    }

    function prevBookPage() {
      currentPage = currentPage === 1 ? 0 : 1;
      renderBooks();
    }

    function showThankYou(e) {
      e.preventDefault();
      const form = e.target;
      const data = new FormData(form);
      fetch(form.action, {
        method: form.method,
        body: data,
        headers: { 'Accept': 'application/json' }
      }).then(response => {
        if (response.ok) {
          document.getElementById("thankYou").style.display = "block";
          form.reset();
          setTimeout(() => { document.getElementById("thankYou").style.display = "none"; }, 5000);
        }
      });
    }

    renderBooks();
  </script>

</body>
</html>
