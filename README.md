# S
from flask import Flask, request, jsonify

app = Flask(__name__)

# قائمة لتخزين الرسائل
messages = []

# نقطة النهاية لجلب الرسائل
@app.route('/messages', methods=['GET'])
def get_messages():
    return jsonify(messages)

# نقطة النهاية لإضافة رسالة
@app.route('/messages', methods=['POST'])
def post_message():
    msg = request.json
    messages.append(msg)
    return jsonify({"status": "Message added"}), 201

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
تطبيقنا الجديد
