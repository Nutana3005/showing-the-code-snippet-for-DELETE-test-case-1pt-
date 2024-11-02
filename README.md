# showing-the-code-snippet-for-DELETE-test-case-1pt-
@app.route("/products", methods=["GET"])
def list_all_products():
    products = Product.query.all()
    return jsonify([product.serialize() for product in products])

@app.route("/products/<int:id>", methods=["DELETE"])
def delete_product(id):
    product = Product.find(id)
    if product:
        product.delete()
    return "", 204
