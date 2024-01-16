# BehaviorTree.ROS2 (forked by David Lai)

This repository is a forked version by David Lai. Changes made in the source code include:
1. bt_topic_sub_node:
    - use RosNodeParams.server_timeout as the sleep duration before the executor spins to receive subscription to avoid failure when ticking the node for the first time.
2. bt_action_node:
    - added a nullptr checking for goal_handle_ before canceling the goal in cancelGoal()
    - added asyncCancelGoal() public function to allow async_cancel_all_goals()
    - temporarily disable oal request timeout check
[![Test](https://github.com/BehaviorTree/BehaviorTree.ROS2/actions/workflows/test.yml/badge.svg)](https://github.com/BehaviorTree/BehaviorTree.ROS2/actions/workflows/test.yml)

This repository contains useful wrappers to use ROS2 and BehaviorTree.CPP together.

In particular, it provides a standard way to implement:

- Action clients.
- Service Clients.
- Topic Subscribers.
- Topic Publishers.

Our main goals are:

- to minimize the amount of boilerplate.
- to make asynchronous Actions non-blocking.

Note that this library is compatible **only** with:

- **BT.CPP** 4.1 or newer.
- **ROS2** Humble or newer.

Additionally, check **plugins.hpp** to see how to learn how to
wrap your Nodes into plugins that can be loaded at run-time.


## Acknowledgements

A lot of code is either inspired or copied from [Nav2](https://navigation.ros.org/).

For this reason, we retain the same license and copyright.


