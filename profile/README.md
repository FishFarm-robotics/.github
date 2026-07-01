# FishFarm Robotics

**SRCP (Semantic Robotics Control Platform)** — 로봇 암 기반 3D 스캐닝을 통한 스마트 양식 객체 디지털 트윈 시스템

동국대학교 종합설계 프로젝트 (석문기 교수님 멘토)

> 양식장 환경을 3D 스캔하여 디지털 트윈을 구축하고, 사용자의 자연어 명령을 해석하여 로봇이 자율 주행하는 통합 플랫폼.
>
> **"어항 앞으로 가줘"** → MASt3R-SLAM 3D 맵 → ULIP 객체 매칭 → PRM 경로 계획 → myAGV 자율 주행

## Team

| Member | Role | Module |
|--------|------|--------|
| 오현석 | SLAM & Robot Control | 1) 3D point cloud 생성 및 SLAM 비교 분석 · 6) ROS 기반 myAGV 운용 |
| 권다훈(Leader) | 3D Preprocessing & Segmentation | 2) 포인트 클라우드 전처리 및 분할 (바닥면 검출 + PointSAM) · 6) ROS 기반 myAGV 운용 |
| 김건우 | Semantic Embedding & NLP | 3) ULIP 의미 정보 임베딩 · 4) 자연어 명령 해석 (Gemini) |
| 백동민 | Path Planning & Map Conversion | 5) PRM 디지털 구현 (3D→2D 맵 변환 + Dijkstra 경로 탐색) · 2) 바닥면 정렬(공동) |

## Repositories

### Perception & Data Pipeline
- **[realsense-streaming-server](https://github.com/FishFarm-robotics/realsense-streaming-server)** — FastAPI + WebSocket server for Intel RealSense D455 RGB-D stream ingestion and real-time depth statistics. *(오현석)*

### 3D Scene Understanding
- **[pointcloud-plane-segmentation](https://github.com/FishFarm-robotics/pointcloud-plane-segmentation)** — Open3D RANSAC multi-plane extraction: floor detection and gravity-alignment of SLAM-reconstructed point clouds to `y = 0`. *(권다훈, 백동민)*
- **[ulip-inference-api](https://github.com/FishFarm-robotics/ulip-inference-api)** — FastAPI serving layer for ULIP point-cloud ↔ text similarity: match a natural-language prompt against reconstructed 3D objects. *(김건우)*

### Navigation
- **[myagv-nav2-prm](https://github.com/FishFarm-robotics/myagv-nav2-prm)** — ROS 2 Nav2 navigation for myAGV with custom PRM global planner: 3D→2D map conversion, KDTree+Dijkstra path planning, and RViz visualization. *(백동민)*

### Foundations
- **[ros2-pubsub-practice](https://github.com/FishFarm-robotics/ros2-pubsub-practice)** — Minimal ROS 2 (rclpy) talker/listener package. *(오현석)*

## System Architecture

```
User ──"어항 앞으로 가줘"──→ Gemini (NLP) ──→ ULIP (Object Matching)
                                                      │
Camera ──→ MASt3R-SLAM ──→ PointSAM (Segmentation) ──┘
               │                                    Target (x,y,z)
               └──→ Floor Alignment ──→ 2D Grid Map ──→ PRM+Dijkstra ──→ Nav2 ──→ myAGV
```

## Stack

`Python` · `FastAPI` · `ROS 2 Humble / Nav2` · `OMPL` · `Open3D` · `OpenCV` · `RealSense D455` · `MASt3R-SLAM` · `ULIP / PointBERT` · `Gemini API` · `KDTree` · `Dijkstra`

## Demo

📹 [시연 영상 (YouTube)](https://www.youtube.com/watch?v=mlT1b75Mjas)
