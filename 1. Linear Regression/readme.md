In this notebook, I explore the implemenation of linear regression model from scratch only using numpy

Reference: http://www.d2l.ai/chapter_linear-networks/linear-regression.html

Formula used along with their code

Forward pass:

<img width="176" alt="forward_pass" src="https://user-images.githubusercontent.com/19811847/150731940-b07a375f-2b78-4565-90a5-35b5208aa60f.PNG">
    
    #Initializing weight and biases
    w = np.random.rand(x.shape[1], 1) 
    b = np.array([0.])
    
    # performing forward pass
    o = np.dot(x, w) + b


Calculating deviation from desired output

    l = o-y

Calculating gradient of loss w.r.t weight and bias using chain rule

    dw = np.dot(x.T, l)
    db = l

Performing gradient descent on weight and biases

    w -= ((lr * dw)/n)
    b -= ((lr * np.sum(db))/n)
