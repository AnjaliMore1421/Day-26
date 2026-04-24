# Day 26 – Frontend Task (10/01/2026)
## Deep Theory Notes

---

# 1. GSAP Timeline Fundamentals

##  GSAP -
GSAP (GreenSock Animation Platform) is a high-performance JavaScript library used to create smooth animations in frontend development.

---

##  Timeline -
A GSAP Timeline is a sequencing tool that allows multiple animations to run in order, overlap, or control timing precisely.

---

## Key Concepts
 
 1) Basic Timeline
```javascript
const tl = gsap.timeline();

tl.to(".box1", { x: 200, duration: 1 })
  .to(".box2", { y: 100, duration: 1 })
  .to(".box3", { opacity: 0, duration: 1 });

2) Why Timeline is used?
Controls sequence of animations
Avoids callback hell
Sync multiple animations easily
Enables complex UI motion design

3) Timeline Features
delay → wait before animation starts
stagger → animate multiple elements one by one
repeat → loop animations
yoyo → reverse animation back and forth
4) Position Control
tl.to(".box1", { x: 100 })
  .to(".box2", { x: 200 }, "-=0.5"); // overlap



2. ScrollTrigger Deep Usage

ScrollTrigger is a GSAP plugin used to trigger animations based on scroll position.

Basic Example
gsap.to(".box", {
  x: 500,
  scrollTrigger: {
    trigger: ".box",
    start: "top 80%",
    end: "top 30%",
    scrub: true
  }
});
Key Properties
1. trigger

Element that activates animation

2. start / end

Defines scroll positions

"top 80%" → animation starts when element reaches 80% viewport
3. scrub
true → animation follows scroll smoothly
4. pin

Fix element during scroll

pin: true
5. toggleActions

Controls play/pause behavior

"play pause resume reset"

Advanced Use Cases -
1)Parallax effects
2)Section-based animations
3)Sticky dashboards
4)Scroll-based charts


3. SVG Animations and Vector Motion

SVG (Scalable Vector Graphics) animations allow smooth, resolution-independent motion.

Methods of SVG Animation
1) CSS Animation
circle {
  animation: move 2s infinite;
}
2) GSAP SVG Animation
gsap.to("#circle", {
  strokeDashoffset: 0,
  duration: 2
});

Important SVG Concepts
1) stroke-dasharray

Used to create dashed paths

2) stroke-dashoffset

Used for drawing effects

Example: Drawing Animation
gsap.fromTo(
  "#path",
  { strokeDashoffset: 1000 },
  { strokeDashoffset: 0, duration: 3 }
);

Use Cases
1)Loader animations
2)Icons animation
3)Logo reveal effects
4)Infographics motion


4. Sequence-Based Animations for Dashboards
 Dashboard Animations -

Animations applied in dashboards to enhance UX and visual storytelling.

Sequence-Based Animation Meaning

Animations that occur step-by-step in a controlled order.

Example using GSAP Timeline -
const tl = gsap.timeline();

tl.from(".card1", { opacity: 0, y: 50 })
  .from(".card2", { opacity: 0, y: 50 })
  .from(".chart", { scale: 0 });

Dashboard Animation Patterns
1) Page Load Sequence
Header appears
Cards animate
Charts load
2) Scroll-based Dashboard
Widgets animate on scroll
Data loads progressively
3) Interactive Animation
Hover effects
Click transitions
Real-time updates
