from flask import Flask, request, jsonify

app = Flask(__name__)

# Simulación de base de datos
books = []

@app.route('/books', methods=['POST'])
def register_book():
    data = request.get_json()
    required_fields = ['title', 'author', 'isbn', 'qr_code']
    if not data or not all(key in data for key in required_fields):
        return jsonify({"error": "Missing data"}), 400
    
    book = {
        'title': data['title'],
        'author': data['author'],
        'isbn': data['isbn'],
        'qr_code': data['qr_code']
    }
    books.append(book)
    return jsonify({"message": "Book registered successfully", "book": book}), 201

if __name__ == '__main__':
    app.run(debug=True)
