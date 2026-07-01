# FishFarm Robotics 🐟🤖

Robotics and 3D-perception work built around an autonomous **fish-farm**
inspection scenario — from RGB-D capture, through SLAM-based 3D reconstruction
and scene understanding, to mobile-robot navigation.

Each repository is a self-contained piece of that pipeline.

## Repositories

### Perception & data pipeline
- **[realsense-streaming-server](https://github.com/FishFarm-robotics/realsense-streaming-server)**
  — FastAPI + WebSocket server that ingests an Intel RealSense **D455** RGB-D
  stream and computes per-frame depth statistics in real time.

### 3D scene understanding
- **[pointcloud-plane-segmentation](https://github.com/FishFarm-robotics/pointcloud-plane-segmentation)**
  — Open3D **RANSAC** multi-plane extraction to detect the floor and
  gravity-align a SLAM-reconstructed point cloud to `y = 0`.
- **[ulip-inference-api](https://github.com/FishFarm-robotics/ulip-inference-api)**
  — FastAPI serving layer for **ULIP** point-cloud ↔ text similarity: match a
  natural-language prompt against reconstructed 3D objects.

### Navigation
- **[myagv-nav2-prm](https://github.com/FishFarm-robotics/myagv-nav2-prm)**
  — ROS 2 **Nav2** navigation for the MyAGV robot on a SLAM-built occupancy grid,
  plus a custom **OMPL PRM** global planner and path-visualization tools.

### Foundations
- **[ros2-pubsub-practice](https://github.com/FishFarm-robotics/ros2-pubsub-practice)**
  — Minimal ROS 2 (rclpy) talker/listener package.

## Stack

`Python` · `FastAPI` · `ROS 2 / Nav2` · `OMPL` · `Open3D` · `OpenCV` ·
`RealSense D455` · `MASt3R-SLAM` · `ULIP`
