# Main-CW




from tensorflow.keras.datasets import cifar10

(X_train, y_train), (X_test, y_test) = cifar10.load_data()

print(X_train.shape, X_test.shape)  # Output: (50000, 32, 32, 3) (10000, 32, 32, 3)
