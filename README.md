# getaname

from flask import Flask
from flask import request
from flask import render_template
import random

app = Flask(__name__)

@app.route('/')
def index():
        return render_template('index.html')
    
@app.route('/getname')
def getname():
    names = ['Daniel','Iker','Iñigo','Gaizka','Josu',
        'Mario', 'Aitor', 'Pablo','Matias', 'Alvaro','Asier']
    random_name = random.choice(names)
    return render_template('getname.html', name=random_name)

@app.route('/friends')
def friends():
    MyFriends = ('Daniel','Iker','Iñigo','Gaizka','Josu',
               'Mario', 'Aitor', 'Pablo','Matias', 'Alvaro','Asier')
    
    return render_template('friends.html',friends=MyFriends)

if __name__ == '__main__':
    app.run(debug=True)
    
