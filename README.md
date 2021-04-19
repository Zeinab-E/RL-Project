This repository includes code for autonomous exploration under uncertainty via Deep Reinforcement Learning (DRL) on Graphs by using a graph neural network (GNN) to represent the state consisting of robot
poses, landmarks, and frontiers. Using deep RL significantly reduces computation as the policy can estimate the optimal view instead of explicitly computing it.
We use the code of original paper wich is available at https://github.com/RobustFieldAutonomyLab/DRL_graph_exploration.

 Dependency
• Python 3
• PyTorch
• Pytorch Geometric
 
       pip install torch-scatter -f https://pytorch-geometric.com/whl/torch-1.7.0+cu102.html
       pip install torch-sparse -f https://pytorch-geometric.com/whl/torch-1.7.0+cu102.html
       pip install torch-cluster -f https://pytorch-geometric.com/whl/torch-1.7.0+cu102.html
       pip install torch-spline-conv -f https://pytorch-geometric.com/whl/torch-1.7.0+cu102.html
       pip install torch-geometric

• Gtsam (Georgia Tech Smoothing and Mapping library)

       git clone -b emex --single-branch https://bitbucket.com/jinkunw/gtsam
       cd gtsam
       mkdir build && cd build
       cmake ..
       sudo make install

• Pybind11(pybind11 — Seamless operability between C++11 and Python)

      git clone https://github.com/pybind/pybind11.git
      cd pybind11
      mkdir build && cd build
      cmake ..
      sudo make install

• flann.hpp

      sudo apt-get install -y libflann-dev



Issues

The code was compiled on a local machine running Ubuntu 20.04 as the operating system with a GTX 3090 GPU with Cuda 11.2 to speed up training/inference with pytorch. However,
because of very large amount of training (1 million epochs as shown in figure 3b in the paper), training was not possible as it took about 2 hours to run for about 12,000 epochs, which is about 83 hours total without checkpointing implemented in
the original code.
Due to the difficulties compiling on a cloud computing server, we trained for a limited number of epochs (10,000) on the local computer with a GPU.

Compile

You can use the following commands to download and compile the package.

      git clone https://github.com/Zeinab-E/CP8319_Project
      cd DRL_graph_exploration
      mkdir build && cd build
      cmake ..
      make

How to run?

• To run the saved policy:

