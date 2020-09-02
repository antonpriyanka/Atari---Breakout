# Atari-Breakout

![Alt Text](https://github.com/antonpriyanka/Atari-Breakout/blob/master/atari-breakout.gif)


# Hyperparamters:

seed = 42<br />
gamma = 0.99  # Discount factor for past rewards<br />
epsilon = 1.0  # Epsilon greedy parameter<br />
epsilon_min = 0.1  # Minimum epsilon greedy parameter<br />
epsilon_max = 1.0  # Maximum epsilon greedy parameter<br />
epsilon_interval = (epsilon_max - epsilon_min)  # Rate at which to reduce chance of random action being taken<br />
batch_size = 32  # Size of batch taken from replay buffer<br />
max_steps_per_episode = 10000<br />


epsilon_random_frames = 50000 # Number of frames to take random action and observe output<br />
epsilon_greedy_frames = 1000000.0 # Number of frames for exploration<br />
max_memory_length = 100000  # Maximum replay length # Note: The Deepmind paper suggests 1000000 however this causes memory issues<br />
update_after_actions = 4  # Train the model after 4 actions<br />
update_target_network = 10000 # How often to update the target network<br />
loss_function = keras.losses.Huber()  # Using huber loss for stability<br />


# Model Architecture
num_actions=4<br />

InputLayer - (84, 84, 4)<br />

ConvolutionalLayer1 - Conv2D(32, 8, strides=4, activation="relu")<br />
ConvolutionalLayer2 - Conv2D(64, 4, strides=2, activation="relu")<br />
ConvolutionalLayer3 - Conv2D(64, 3, strides=1, activation="relu")<br />
Flatten()<br />
DenseLayer - Dense(512, activation="relu")<br />

OutputLayer - Dense(num_actions, activation="linear")<br />


I had to train this model in colab Pro for 10million frames. It took me around 4 days due to environment limitations. I did lose my replay buffer since colab's runtime is limited to 24 hours.

Will be uploading my model checkpoints soon.





