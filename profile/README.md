# FishFarm Robotics 🐟🤖

**SRCP (Semantic Robotics Control Platform)** — 로봇 암 기반 3D 스캐닝을 통한 스마트 양식 객체 디지털 트윈 시스템

## System Architecture

![SRCP System Architecture](https://raw.githubusercontent.com/FishFarm-robotics/.github/main/profile/architecture.png)

> **"어항 앞으로 가줘"** 한마디로 로봇이 자율 주행합니다.
>
> Camera → MASt3R-SLAM 3D 재구성 → PointSAM 객체 분할 → ULIP 의미 매칭 → Gemini 자연어 해석 → PRM+Dijkstra 경로 계획 → ROS Nav2 → myAGV 주행

## Repositories

| Repository | Description | Contributor |
|------------|-------------|-------------|
| [realsense-streaming-server](https://github.com/FishFarm-robotics/realsense-streaming-server) | Intel RealSense D455 RGB-D 스트림 수신 서버 (FastAPI + WebSocket) | 오현석 |
| [pointcloud-plane-segmentation](https://github.com/FishFarm-robotics/pointcloud-plane-segmentation) | RANSAC 바닥면 검출 + 회전행렬 정렬 (Open3D) | 권다훈, 백동민 |
| [ulip-inference-api](https://github.com/FishFarm-robotics/ulip-inference-api) | ULIP point-cloud ↔ text 유사도 매칭 서버 (FastAPI) | 김건우 |
| [myagv-nav2-prm](https://github.com/FishFarm-robotics/myagv-nav2-prm) | 3D→2D 맵 변환 + PRM+Dijkstra 경로 계획 + Nav2 주행 (ROS 2) | 백동민 |
| [ros2-pubsub-practice](https://github.com/FishFarm-robotics/ros2-pubsub-practice) | ROS 2 기초 통신 연습 (rclpy) | 오현석 |

## Team

동국대학교 종합설계 프로젝트 (석문기 교수님 멘토)

| Member | Role |
|--------|------|
| 오현석 | ① SLAM 비교 분석 (MASt3R-SLAM 선정) · ⑥ ROS 기반 myAGV 운용 |
| 권다훈 | ② 포인트 클라우드 전처리/분할 (바닥면 검출 + PointSAM) |
| 김건우 | ③ ULIP 의미 임베딩 · ④ 자연어 명령 해석 (Gemini API) |
| 백동민 | ⑤ PRM 경로 계획 (3D→2D 맵 변환 + Dijkstra) · ② 바닥면 정렬(공동) |

## Stack

`Python` · `FastAPI` · `ROS 2 Humble / Nav2` · `OMPL` · `Open3D` · `OpenCV` · `RealSense D455` · `MASt3R-SLAM` · `ULIP / PointBERT` · `Gemini API` · `KDTree` · `Dijkstra`

## Demo

📹 [시연 영상 (YouTube)](https://www.youtube.com/watch?v=mlT1b75Mjas)
