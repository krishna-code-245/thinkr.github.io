from flask import Flask, render_template_string

app = Flask(__name__)

# HTML template as a string
html_template = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My GitHub Page</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f9f9f9; }
    header { background: #24292e; color: #fff; padding: 20px; text-align: center; }
    nav { background: #0366d6; display: flex; justify-content: center; }
    nav a { color: #fff; padding: 14px 20px; text-decoration: none; }
    nav a:hover { background: #024ea2; }
    .container { max-width: 1000px; margin: auto; padding: 20px; }
    .content { display: flex; flex-wrap: wrap; gap: 20px; }
    .main { flex: 3; background: #fff; padding: 20px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
    .sidebar { flex: 1; background: #eaeaea; padding: 20px; border-radius: 8px; }
    footer { background: #24292e; color: #fff; text-align: center; padding: 10px; margin-top: 20px; }
  </style>
</head>
<body>
  <header>
    <h1>Welcome to My GitHub Page</h1>
    <p>Hosted with Flask & GitHub Pages</p>
  </header>
  <nav>
    <a href="#">Home</a>
    <a href="#">Projects</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </nav>
  <div class="container">
    <div class="content">
      <div class="main">
        <h2>Main Content</h2>
        <p>This is where you can showcase your projects, write blogs, or share updates.</p>
      </div>
      <div class="sidebar">
        <h2>Sidebar</h2>
        <p>Quick links, GitHub profile, or social media can go here.</p>
      </div>
    </div>
  </div>
  <footer>
    <p>&copy; 2026 Your Name | Powered by Flask</p>
  </footer>
</body>
</html>
"""

@app.route("/")
def home():
    return render_template_string(html_template)

if __name__ == "__main__":
    app.run(debug=True)

