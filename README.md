<img width="3188" height="1202" alt="frame (3)" src="https://github.com/user-attachments/assets/517ad8e9-ad22-457d-9538-a9e62d137cd7" />


# EQQ 🎯


## Basic Details
### Team Name: Ren


### Team Members
- Team Lead: Reno - Mar Baselios College of Engineering and Technology, Kuttikkanam
- Member 2: [Name] - [College]
- Member 3: [Name] - [College]

### Project Description
you can crack and hatch an egg.

### The Problem (that doesn't exist)
after the egg hatches, the new egg is empty.

### The Solution (that nobody asked for)
The first Egg had Chick inside.
## Technical Details
### Technologies/Components Used
For Software:
- html
- css
- python
- [Tools used]

For Hardware:
- [List main components]
- [List specifications]
- [List tools required]

### Implementation
For Software:
# Installation
[commands]

# Run
[commands]

### Project Documentation
For Software:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>hATCH ME</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Luckiest+Guy&family=Inter:wght@400;700&display=swap');

      body {
            font-family: 'Inter', sans-serif;
            background-color: #a8d5e5;
            position: relative;
            overflow: hidden;
        }

        h1 {
            font-family: 'Luckiest Guy', cursive;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            50% { transform: translateX(5px); }
            75% { transform: translateX(-5px); }
        }

        @keyframes bob {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        @keyframes eat {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(10px) rotate(5deg); }
        }
        
        @keyframes moveCloudLeft {
            from { transform: translateX(0); }
            to { transform: translateX(-150vw); }
        }

        @keyframes moveCloudRight {
            from { transform: translateX(0); }
            to { transform: translateX(150vw); }
        }
        
        @keyframes flyAcross {
            0% { transform: translate(-100vw, 50px); }
            100% { transform: translate(100vw, 150px); }
        }
        
        @keyframes flap {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(-20deg); }
        }
        
        @keyframes crowFly {
            0% { transform: translateX(-100vw); }
            100% { transform: translateX(100vw); }
        }

        .egg-container {
            width: 200px;
            height: 350px;
            cursor: pointer;
            position: absolute;
            right: 2%; 
            bottom: -50px;
            transition: transform 0.2s ease-in-out;
            transform-style: preserve-3d;
            z-index: 3;
        }
        
        .egg-container.shake {
            animation: shake 0.2s ease-in-out;
        }

        .egg-container:hover {
             transform: translateY(-5px);
        }

        .egg {
            width: 100%;
            height: 100%;
            background-color: #f4e8d8;
            border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
            box-shadow: inset 0 -10px 10px rgba(0,0,0,0.1),
                        0 10px 20px rgba(0,0,0,0.1);
            position: absolute;
            top: 0;
            left: 0;
            transition: opacity 0.5s ease-in-out;
        }

        .egg.hatched {
            opacity: 0;
        }

        .egg-shell-top,
        .egg-shell-bottom {
            position: absolute;
            width: 100%;
            height: 50%;
            background-color: #f4e8d8;
            transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
            z-index: 10;
        }

        .egg-shell-top {
            top: 0;
            border-radius: 50% 50% 50% 50% / 90% 90% 0 0;
            clip-path: polygon(0 0, 100% 0, 100% 70%, 0 70%);
            transform: translateY(0);
        }

        .egg-shell-bottom {
            bottom: 0;
            border-radius: 50% 50% 50% 50% / 0 0 90% 90%;
            clip-path: polygon(0 30%, 100% 30%, 100% 100%, 0 100%);
            transform: translateY(0);
        }

        .hatched .egg-shell-top {
            transform: translateY(-60px) rotate(15deg);
        }

        .hatched .egg-shell-bottom {
            transform: translateY(60px) rotate(-15deg);
        }
        
        .hide-shell {
            opacity: 0;
            transform: translateY(0) scale(0);
        }

        .chick {
            width: 120px;
            height: 120px;
            background-color: #fce47c;
            border-radius: 50%;
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%) translateY(100%);
            opacity: 0;
            transition: transform 0.7s ease-in-out, opacity 0.7s ease-in-out, background-color 0.5s ease-in-out;
        }

        .hatched .chick {
            opacity: 1;
            transform: translateX(-50%) translateY(0);
        }

        .chick.rooster {
            width: 160px;
            height: 160px;
            background-color: #fce47c;
            border-radius: 50% 50% 40% 40% / 60% 60% 40% 40%;
            transform: translateX(-50%) scale(1.2) translateY(-20px); 
            animation: bob 1s ease-in-out infinite;
            transition: transform 1s ease-in-out, background-color 1s ease-in-out;
        }
        
        .chick.rooster.standing-still {
            animation: none;
            transform: translateX(-50%) scale(1.2) translateY(-20px);
        }

        .chick-eye {
            width: 12px;
            height: 12px;
            background-color: #333;
            border-radius: 50%;
            position: absolute;
            top: 40px;
        }

        .chick-eye.left { left: 28px; }
        .chick-eye.right { right: 28px; }

        .chick-beak {
            width: 0;
            height: 0;
            border-left: 12px solid transparent;
            border-right: 12px solid transparent;
            border-bottom: 16px solid #f16a04;
            position: absolute;
            top: 55px;
            left: 50%;
            transform: translateX(-50%);
        }

        .chick-wing {
            width: 30px;
            height: 15px;
            background-color: #fce47c;
            border-radius: 5px;
            position: absolute;
            top: 60px;
            z-index: -1;
            transition: transform 0.5s ease-in-out;
        }

        .chick-wing.left {
            left: -10px;
            transform: rotate(-15deg);
        }
        .chick-wing.right {
            right: -10px;
            transform: rotate(-15deg);
        }

        .chick-leg {
            width: 4px;
            height: 20px;
            background-color: #f16a04;
            position: absolute;
            bottom: -20px;
            transform-origin: top;
            transition: transform 0.5s ease-in-out;
        }

        .chick-leg.left {
            left: 45px;
            transform: rotate(15deg);
        }
        .chick-leg.right {
            right: 45px;
            transform: rotate(-15deg);
        }

        .chick-comb, .chick-wattle, .chick-tail {
            position: absolute;
            background-color: #ff0000;
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
        }

        .chick-comb {
            width: 25px;
            height: 12px;
            border-radius: 50% 50% 0 0 / 100% 100% 0 0;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
        }

        .chick-wattle {
            width: 8px;
            height: 12px;
            border-radius: 50%;
            top: 65px;
        }

        .chick-wattle.left {
            left: 45px;
        }

        .chick-wattle.right {
            right: 45px;
        }

        .chick-tail {
            width: 0;
            height: 0;
            border-left: 16px solid transparent;
            border-right: 16px solid transparent;
            border-bottom: 32px solid #fce47c;
            position: absolute;
            top: 60px;
            right: -25px;
            transform: rotate(90deg);
        }
        
        .chick.rooster .chick-comb,
        .chick.rooster .chick-wattle,
        .chick.rooster .chick-tail {
            opacity: 1;
        }

        .speech-bubble {
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%) scale(0);
            transform-origin: bottom;
            background-color: #fff;
            padding: 10px 15px;
            border-radius: 20px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            opacity: 0;
            transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
        }
        
        .speech-bubble.show-bubble {
            transform: translateX(-50%) scale(1);
            opacity: 1;
        }

        .speech-bubble::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 0;
            border-left: 10px solid transparent;
            border-right: 10px solid transparent;
            border-top: 10px solid #fff;
        }
        
        .sun {
            position: absolute;
            top: 50px;
            left: 10%;
            width: 100px;
            height: 100px;
            background-color: #ffeb3b;
            border-radius: 50%;
            box-shadow: 0 0 50px 10px #ff9800;
            z-index: -1;
        }

        .cloud {
            position: absolute;
            z-index: -1;
        }

        .cloud.moving-right {
            animation: moveCloudRight 60s linear infinite;
        }

        .cloud.moving-left {
            top: 10%;
            left: 100%;
            animation: moveCloudLeft 60s linear infinite;
        }

        .cloud-body {
            position: relative;
            background: #fff;
            width: 120px;
            height: 40px;
            border-radius: 40px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .cloud.large .cloud-body {
            width: 150px;
            height: 50px;
        }

        .cloud-body::before,
        .cloud-body::after {
            content: '';
            position: absolute;
            background: #fff;
            border-radius: 50%;
        }

        .cloud-body::before {
            width: 60px;
            height: 60px;
            top: -30px;
            left: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .cloud.large .cloud-body::before {
            width: 75px;
            height: 75px;
        }

        .cloud-body::after {
            width: 80px;
            height: 80px;
            top: -40px;
            right: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .cloud.large .cloud-body::after {
            width: 100px;
            height: 100px;
        }

        .cloud.still-1 {
            top: 15%;
            left: 5%;
        }
        .cloud.moving-right {
            top: 25%;
            left: -20%;
        }
        .cloud.moving-left {
            top: 10%;
            left: 100%;
        }
        .cloud.still-4 {
            top: 20%;
            left: 30%;
        }
        .cloud.still-5 {
            top: 15%;
            left: 45%;
        }
        .cloud.still-6 {
            top: 30%;
            left: 90%;
        }
        .cloud.still-7 {
            top: 5%;
            right: 10%;
        }


        .ground-container {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 30vh;
            z-index: -2;
            overflow: hidden;
        }
        
        .hill {
            position: absolute;
            bottom: -50px;
            border-radius: 50%;
            box-shadow: inset 0 10px 20px rgba(0,0,0,0.1);
        }

        .hill-1 {
            width: 150%;
            height: 350px; 
            background-color: #8FBC8F;
            left: -20%;
            z-index: -1;
        }

        .hill-2 {
            width: 120%;
            height: 300px;
            background-color: #6B8E23;
            right: -20%;
            z-index: -1;
        }
        
        .hut {
            position: absolute;
            right: 15%;
            bottom: 40px;
            width: 150px;
            z-index: 1;
        }
        
        .hut-body {
            width: 100%;
            height: 130px;
            background-color: #8B4513;
            border-radius: 5px;
            position: relative;
            box-shadow: 0 5px 10px rgba(0,0,0,0.2);
        }
        
        .hut-roof {
            width: 180px;
            height: 0;
            border-left: 75px solid transparent;
            border-right: 75px solid transparent;
            border-bottom: 75px solid #A0522D;
            position: absolute;
            top: -75px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 2;
        }
        
        .hut-door {
            width: 50px;
            height: 75px;
            background-color: #5C3317;
            border-radius: 5px 5px 0 0;
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .hut-window {
            width: 35px;
            height: 35px;
            background-color: #e0e0e0;
            border-radius: 50%;
            position: absolute;
            top: 30px;
            left: 30px;
            border: 2px solid #5C3317;
        }

        .cow {
            position: absolute;
            bottom: 70px;
            width: 120px;
            height: 80px;
            z-index: 1;
        }
        
        .cow.cow-left {
            left: 15%;
            bottom: 120px;
            width: 80px;
            height: 50px;
            z-index: 0;
        }

        .cow.cow-right-1 {
            right: 35%;
            bottom: 10px;
            transform: scaleX(-1);
        }

        .cow.cow-right-2 {
            right: 5%;
            bottom: 0;
            transform: scaleX(-1) scale(0.8);
            z-index: 0;
        }

        .cow-body {
            position: absolute;
            width: 100%;
            height: 100%;
            background-color: #fff;
            border-radius: 50% 50% 30% 30% / 60% 60% 40% 40%;
            box-shadow: 0 5px 10px rgba(0,0,0,0.1);
        }

        .cow-head {
            position: absolute;
            width: 40px;
            height: 50px;
            background-color: #fff;
            border-radius: 50%;
            top: 10px;
            left: 80%;
            transform-origin: top left;
            animation: eat 1.5s ease-in-out infinite;
        }

        .cow-eye {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: #000;
            border-radius: 50%;
            top: 15px;
            z-index: 1;
        }
        
        .cow-eye.left {
            left: 10px;
        }
        
        .cow-eye.right {
            right: 10px;
        }

        .cow-ear {
            position: absolute;
            width: 15px;
            height: 10px;
            background-color: #000;
            border-radius: 50%;
            top: -5px;
            z-index: -1;
        }

        .cow-ear.left {
            left: 15px;
            transform: rotate(-15deg);
        }
        .cow-ear.right {
            right: 5px;
            transform: rotate(15deg);
        }

        .cow-snout {
            position: absolute;
            width: 15px;
            height: 10px;
            background-color: #ffc0cb;
            border-radius: 50%;
            bottom: 5px;
            left: 50%;
            transform: translateX(-50%);
        }

        .cow-spot {
            position: absolute;
            background-color: #000;
            border-radius: 50%;
        }

        .cow-spot.spot-1 {
            width: 25px;
            height: 25px;
            top: 20px;
            left: 20px;
        }

        .cow-spot.spot-2 {
            width: 35px;
            height: 35px;
            top: 40px;
            left: 60px;
        }

        .cow-spot.spot-3 {
            width: 20px;
            height: 20px;
            bottom: 10px;
            right: 15px;
        }

        .cow-leg {
            position: absolute;
            width: 15px;
            height: 30px;
            background-color: #fff;
            bottom: -10px;
            border-radius: 5px;
            box-shadow: 0 5px 10px rgba(0,0,0,0.1);
        }

        .cow-leg.front-left { left: 15px; }
        .cow-leg.front-right { left: 35px; }
        .cow-leg.back-left { right: 35px; }
        .cow-leg.back-right { right: 15px; }
        
        .flying-bird {
            position: absolute;
            top: 15%;
            left: -10%;
            width: 30px;
            height: 30px;
            z-index: -1;
            animation: flyAcross 20s linear infinite, flap 0.5s ease-in-out infinite;
        }

        .flying-bird svg {
            width: 100%;
            height: 100%;
            fill: #4b5563;
        }
        
        .flying-crow {
            position: absolute;
            width: 40px;
            height: 40px;
            z-index: 0;
            top: 25%;
            left: -10%;
        }
        
        .flying-crow svg {
            width: 100%;
            height: 100%;
            fill: #000;
        }
        
        .crow-1 {
            animation: crowFly 30s linear infinite, flap 0.5s ease-in-out infinite;
        }
        
        .crow-2 {
            top: 20%;
            animation: crowFly 35s linear infinite 5s, flap 0.5s ease-in-out infinite;
        }
    </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen text-gray-800">

    <div class="sun"></div>
    <div class="cloud still-1"><div class="cloud-body"></div></div>
    <div class="cloud moving-right large"><div class="cloud-body"></div></div>
    <div class="cloud moving-left"><div class="cloud-body"></div></div>
    <div class="cloud still-4 large"><div class="cloud-body"></div></div>
    <div class="cloud still-5"><div class="cloud-body"></div></div>
    <div class="cloud still-6 large"><div class="cloud-body"></div></div>
    <div class="cloud still-7 large"><div class="cloud-body"></div></div>
    
    <div class="flying-bird">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
            <path d="M512 240c0-10.7-3.9-21.3-11.4-29.6l-144-160c-15-16.7-41.9-17.9-58.6-2.9s-17.9 41.9-2.9 58.6l106.6 118.5-224 0c-22.1 0-40 17.9-40 40s17.9 40 40 40l224 0L295.1 432c-15 16.7-13.8 43.6 2.9 58.6s43.6 13.8 58.6-2.9l144-160C508.1 261.3 512 250.7 512 240z"/>
        </svg>
    </div>
    
    <div class="flying-crow crow-1">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
            <path d="M495.1 234.3c-2.3-5.2-12.7-8.9-18.7-22.7-2.6-6-2.4-12.1-.9-18.1 5.8-22.6 13.9-48.5 13.9-74.9 0-45.9-22-83.3-46.7-109.1-8.5-9.2-22.4-10-31.5-1.5s-10 22.4-1.5 31.5c16.3 17.5 33.4 46.4 33.4 79.1 0 16.2-3.8 31.6-11.4 46.5-6 12.1-15.3 19.3-25.1 23.3-9.7 3.9-19.8 4.2-28.7 1.1-10.7-3.7-20.9-12.9-26.6-22.1-17.5-28.5-27-62.9-27-98.3 0-66.2 36.3-120 81.1-147.2 13.2-8.3 29.3-5.6 38.3 6.1 9.1 11.6 6.3 27.6-6.8 35.9-28.7 18-50.5 50.4-50.5 83.1 0 29.1 8.2 56.4 22.8 80.5-20.2 11.9-41 18.2-62.1 18.2-16.7 0-33.1-3.6-48.4-10.7-24.3-11.2-46.3-29.7-65.7-54.7-5.5-7.2-14.8-10.8-23.7-9.4-8.8 1.4-16 7.4-19.8 15.6-35.8 77.2-4.1 163 70 209.6 2.8 1.7 5.7 3.2 8.7 4.5 14.1 6.1 28.5 9.1 43.1 9.1 16.5 0 32.8-4.2 47.7-12.5 13.1-7.2 24.3-17.3 33.4-29.9 8.2-11.2 15-23.4 20.3-36.5-11 5.3-22.9 8.1-35.2 8.1-23.9 0-45.6-7.8-63.5-20.9-26.1-18.7-44.5-45.9-53.1-76.3-2.9-10.4-13.8-15.3-24.2-12.4s-15.3 13.8-12.4 24.2c9.5 34.2 29.3 64.9 56.4 87.7 22.6 18.9 49.3 28.7 77.2 28.7 13.9 0 27.8-2.6 40.9-7.8 28-10.9 51.5-29.2 68.7-51.5 1.5-1.5 3-3.1 4.5-4.8 16.7-18.7 26.6-43.2 26.6-69.5 0-21.7-5.6-42.3-16-60.5-8.8-15.1-21.2-27.4-36-36.2-22.1-12.8-47.5-19.8-74.1-19.8-14.3 0-28.4 2.8-41.9 8.4-11.2 4.6-21.7 11.2-31.4 19.8-13.6 11.2-24.8 24.6-32.9 39.7-4.1 7.4-13.8 10.6-21.2 6.5s-10.6-13.8-6.5-21.2c8.8-15.8 20.9-30.2 35.8-42.1 11.1-8.7 23.3-15.5 36.3-20.3 17.5-6.6 35.7-9.8 54.2-9.8 26.3 0 51.5 6.4 74.3 19.3 18.5 10.2 34.6 23.9 47.1 41.5 12.5 17.6 19.8 37.8 19.8 59.8 0 28.9-10.3 56.2-29.2 77.1-1.5 1.6-3 3.1-4.7 4.5-25.1 21.2-56.5 33.1-88.7 33.1-22.2 0-43.5-5.7-62-16.7-19.3-11.5-35.8-27.1-49-45.7-7.6-10.4-20.9-12.1-31.3-4.5-10.4 7.6-12.1 20.9-4.5 31.3 15.6 21.4 34.4 39.8 56.2 55.4 19.3 13.7 41.3 22.3 64.9 22.3 35 0 68.1-13.3 93.3-37.1 4.5-4.2 9-8.7 13.5-13.3 14.5-14.9 27.6-31 39.1-48.8 5.7-8.9 13.3-15.8 22.3-20.2 12.5-6.1 26.1-9.6 40.5-9.6 14.3 0 28.2 3.4 41.2 9.6 12.1 5.9 22.9 14.3 31.9 24.8 10.1 11.9 17.8 25.1 22.9 39.3 4.2 11.5 6.3 23.8 6.3 36.2 0 10.4-1.2 20.6-3.6 30.6-2.5 10.6-10.5 18.9-20.9 22.8-10.4 3.8-21.7 2.1-30.8-4.5z"/>
        </svg>
    </div>
    <div class="flying-crow crow-2">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
            <path d="M495.1 234.3c-2.3-5.2-12.7-8.9-18.7-22.7-2.6-6-2.4-12.1-.9-18.1 5.8-22.6 13.9-48.5 13.9-74.9 0-45.9-22-83.3-46.7-109.1-8.5-9.2-22.4-10-31.5-1.5s-10 22.4-1.5 31.5c16.3 17.5 33.4 46.4 33.4 79.1 0 16.2-3.8 31.6-11.4 46.5-6 12.1-15.3 19.3-25.1 23.3-9.7 3.9-19.8 4.2-28.7 1.1-10.7-3.7-20.9-12.9-26.6-22.1-17.5-28.5-27-62.9-27-98.3 0-66.2 36.3-120 81.1-147.2 13.2-8.3 29.3-5.6 38.3 6.1 9.1 11.6 6.3 27.6-6.8 35.9-28.7 18-50.5 50.4-50.5 83.1 0 29.1 8.2 56.4 22.8 80.5-20.2 11.9-41 18.2-62.1 18.2-16.7 0-33.1-3.6-48.4-10.7-24.3-11.2-46.3-29.7-65.7-54.7-5.5-7.2-14.8-10.8-23.7-9.4-8.8 1.4-16 7.4-19.8 15.6-35.8 77.2-4.1 163 70 209.6 2.8 1.7 5.7 3.2 8.7 4.5 14.1 6.1 28.5 9.1 43.1 9.1 16.5 0 32.8-4.2 47.7-12.5 13.1-7.2 24.3-17.3 33.4-29.9 8.2-11.2 15-23.4 20.3-36.5-11 5.3-22.9 8.1-35.2 8.1-23.9 0-45.6-7.8-63.5-20.9-26.1-18.7-44.5-45.9-53.1-76.3-2.9-10.4-13.8-15.3-24.2-12.4s-15.3 13.8-12.4 24.2c9.5 34.2 29.3 64.9 56.4 87.7 22.6 18.9 49.3 28.7 77.2 28.7 13.9 0 27.8-2.6 40.9-7.8 28-10.9 51.5-29.2 68.7-51.5 1.5-1.5 3-3.1 4.5-4.8 16.7-18.7 26.6-43.2 26.6-69.5 0-21.7-5.6-42.3-16-60.5-8.8-15.1-21.2-27.4-36-36.2-22.1-12.8-47.5-19.8-74.1-19.8-14.3 0-28.4 2.8-41.9 8.4-11.2 4.6-21.7 11.2-31.4 19.8-13.6 11.2-24.8 24.6-32.9 39.7-4.1 7.4-13.8 10.6-21.2 6.5s-10.6-13.8-6.5-21.2c8.8-15.8 20.9-30.2 35.8-42.1 11.1-8.7 23.3-15.5 36.3-20.3 17.5-6.6 35.7-9.8 54.2-9.8 26.3 0 51.5 6.4 74.3 19.3 18.5 10.2 34.6 23.9 47.1 41.5 12.5 17.6 19.8 37.8 19.8 59.8 0 28.9-10.3 56.2-29.2 77.1-1.5 1.6-3 3.1-4.7 4.5-25.1 21.2-56.5 33.1-88.7 33.1-22.2 0-43.5-5.7-62-16.7-19.3-11.5-35.8-27.1-49-45.7-7.6-10.4-20.9-12.1-31.3-4.5-10.4 7.6-12.1 20.9-4.5 31.3 15.6 21.4 34.4 39.8 56.2 55.4 19.3 13.7 41.3 22.3 64.9 22.3 35 0 68.1-13.3 93.3-37.1 4.5-4.2 9-8.7 13.5-13.3 14.5-14.9 27.6-31 39.1-48.8 5.7-8.9 13.3-15.8 22.3-20.2 12.5-6.1 26.1-9.6 40.5-9.6 14.3 0 28.2 3.4 41.2 9.6 12.1 5.9 22.9 14.3 31.9 24.8 10.1 11.9 17.8 25.1 22.9 39.3 4.2 11.5 6.3 23.8 6.3 36.2 0 10.4-1.2 20.6-3.6 30.6-2.5 10.6-10.5 18.9-20.9 22.8-10.4 3.8-21.7 2.1-30.8-4.5z"/>
        </svg>
    </div>
    
    <div class="ground-container">
        <div class="hill hill-1"></div>
        <div class="hill hill-2"></div>
    </div>
    
    <div class="hut">
        <div class="hut-body">
            <div class="hut-door"></div>
            <div class="hut-window"></div>
        </div>
        <div class="hut-roof"></div>
    </div>
    
    <div class="cow cow-left">
        <div class="cow-body">
            <div class="cow-spot spot-1"></div>
            <div class="cow-spot spot-2"></div>
            <div class="cow-spot spot-3"></div>
        </div>
        <div class="cow-head">
            <div class="cow-eye left"></div>
            <div class="cow-eye right"></div>
            <div class="cow-ear left"></div>
            <div class="cow-ear right"></div>
            <div class="cow-snout"></div>
        </div>
        <div class="cow-leg front-left"></div>
        <div class="cow-leg front-right"></div>
        <div class="cow-leg back-left"></div>
        <div class="cow-leg back-right"></div>
    </div>

    <div class="cow cow-right-1">
        <div class="cow-body">
            <div class="cow-spot spot-1"></div>
            <div class="cow-spot spot-2"></div>
            <div class="cow-spot spot-3"></div>
        </div>
        <div class="cow-head">
            <div class="cow-eye left"></div>
            <div class="cow-eye right"></div>
            <div class="cow-ear left"></div>
            <div class="cow-ear right"></div>
            <div class="cow-snout"></div>
        </div>
        <div class="cow-leg front-left"></div>
        <div class="cow-leg front-right"></div>
        <div class="cow-leg back-left"></div>
        <div class="cow-leg back-right"></div>
    </div>
    
    <div class="cow cow-right-2">
        <div class="cow-body">
            <div class="cow-spot spot-1"></div>
            <div class="cow-spot spot-2"></div>
            <div class="cow-spot spot-3"></div>
        </div>
        <div class="cow-head">
            <div class="cow-eye left"></div>
            <div class="cow-eye right"></div>
            <div class="cow-ear left"></div>
            <div class="cow-ear right"></div>
            <div class="cow-snout"></div>
        </div>
        <div class="cow-leg front-left"></div>
        <div class="cow-leg front-right"></div>
        <div class="cow-leg back-left"></div>
        <div class="cow-leg back-right"></div>
    </div>
    
    <h1 class="text-4xl md:text-5xl mt-16 mb-2 text-blue-900">hATCH ME</h1>
    <p id="click-message" class="text-lg text-gray-600 mb-8">Click the egg to see what's inside!</p>

    <div id="egg-container" class="egg-container mx-auto relative z-10">
        <div id="egg" class="egg"></div>

        <div id="chick-container" class="relative w-full h-full flex flex-col items-center justify-end overflow-hidden">
            <div id="egg-shell-top" class="egg-shell-top"></div>
            <div id="chick" class="chick flex justify-center items-center">
                <div class="chick-eye left"></div>
                <div class="chick-eye right"></div>
                <div class="chick-beak"></div>
                <div class="chick-wing left"></div>
                <div class="chick-wing right"></div>
                <div class="chick-leg left"></div>
                <div class="chick-leg right"></div>
                <div class="chick-comb"></div>
                <div class="chick-wattle left"></div>
                <div class="chick-wattle right"></div>
                <div class="chick-tail"></div>
                <div id="rooster-speech-bubble" class="speech-bubble"></div>
            </div>
            <div id="egg-shell-bottom" class="egg-shell-bottom"></div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const eggContainer = document.getElementById('egg-container');
            const fullEgg = document.getElementById('egg');
            const chickContainer = document.getElementById('chick-container');
            const chickElement = document.getElementById('chick');
            const eggShellTop = document.getElementById('egg-shell-top');
            const eggShellBottom = document.getElementById('egg-shell-bottom');
            const clickMessage = document.getElementById('click-message');
            const roosterSpeechBubble = document.getElementById('rooster-speech-bubble');
            
            let clickCount = 0;

            const handleEggClick = () => {
                if (eggContainer.style.cursor === 'default') {
                    return;
                }

                if (clickCount < 3) {
                    clickCount++;
                    
                    if (clickCount === 3) {
                        clickMessage.textContent = "It's a chick! Aww!";
                        fullEgg.classList.add('hatched');
                        chickContainer.classList.add('hatched');
                        
                        eggContainer.style.cursor = 'default';
                        
                        setTimeout(() => {
                            growChick();
                        }, 1000);
                    } else {
                        eggContainer.classList.add('shake');
                        setTimeout(() => {
                            eggContainer.classList.remove('shake');
                        }, 200);
                    }
                }
            };
            
            const growChick = () => {
                clickMessage.textContent = "The chick is growing!";
                chickElement.classList.add('rooster');
                
                setTimeout(() => {
                    chickElement.classList.add('standing-still');
                    layNewEgg();
                }, 2000);
            };

            const layNewEgg = () => {
                roosterSpeechBubble.textContent = "BYE!";
                roosterSpeechBubble.classList.add('show-bubble');
                
                setTimeout(() => {
                    chickElement.style.opacity = 0;
                    eggShellTop.classList.add('hide-shell');
                    eggShellBottom.classList.add('hide-shell');
                    roosterSpeechBubble.classList.remove('show-bubble');
                }, 1000);
                
                clickCount = 0;
                
                setTimeout(() => {
                    clickMessage.textContent = "Click the egg to see what's inside!";
                    fullEgg.classList.remove('hatched');
                    chickContainer.classList.remove('hatched');
                    
                    chickElement.classList.remove('rooster', 'standing-still');
                    chickElement.style.opacity = 0;
                    
                    eggShellTop.classList.remove('hide-shell');
                    eggShellBottom.classList.remove('hide-shell');
                    
                    eggContainer.style.cursor = 'pointer';
                }, 2000);
            };

            eggContainer.addEventListener('click', handleEggClick);
        });
    </script>
</body>
</html>

# Screenshots (Add at least 3)
https://drive.google.com/file/d/1w6PKeNjDXax7A6ryEjnGJpW0ZnUtBMJq/view?usp=drive_link
First look of page

https://drive.google.com/file/d/1MUHT0o9vfayoDuHj-fplsyZBgPzIrrZM/view?usp=drive_link
after clicking 3 times the egg hatches

https://drive.google.com/file/d/1EtDbGTqw8xaFb0-Ar9HcJZnZ8Vs0ZdTQ/view?usp=drive_link
egg hatches and the chick grows to final form

# Diagrams
![Workflow](Add your workflow/architecture diagram here)
*Add caption explaining your workflow*

For Hardware:

# Schematic & Circuit
![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

# Build Photos
![Components](Add photo of your components here)
*List out all components shown*

![Build](Add photos of build process here)
*Explain the build steps*

![Final](Add photo of final product here)
*Explain the final build*

### Project Demo
# Video
https://drive.google.com/file/d/106fAZGfUtMgskR9kILEH98t0eRPJFPNW/view?usp=drive_link
Working of the program
# Additional Demos
[Add any extra demo materials/links]

## Team Contributions
- Reno: Full work
- 

---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--25-25?link=https%3A%2F%2Fwww.tinkerhub.org%2Fevents%2FQ2Q1TQKX6Q%2FUseless%2520Projects)



