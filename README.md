from flask import Flask, render_template, request, redirect, url_for

app = Flask(__name__)

# Dummy data for demonstration
posts = [
    {"title": "First Post", "content": "This is the first post content."},
    {"title": "Second Post", "content": "This is the second post content."}
]

@app.route('/')
def index():
    return render_template('index.html', posts=posts)

@app.route('/post/<int:post_id>')
def post(post_id):
    post = posts[post_id]
    return render_template('post.html', post=post)

if __name__ == '__main__':
    app.run(debug=True)
