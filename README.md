# Rotational Motion

This is an interactive, browser-based demo of rotational motion. It covers angular variables, rotational inertia, torque, work and power in rotation, rolling, angular momentum, and gyroscope precession. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 회전 운동학, 선변수와 각변수, 회전관성, 여러 모양의 회전관성, 평행축 정리, 토크와 τ = Iα, 질량이 있는 도르래, 일과 회전운동에너지, 굴림운동, 경사면 굴림 경주, 각운동량 보존, 자이로스코프의 축돌기 운동을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `rotation-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `rotation-en.html` | American English version |
| `rotation-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars, radical signs, and stacked sub- and superscripts, and halves are written as (1/2).

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/rotation-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/rotation-en.html` or `.../rotation-ko.html`.

These pages can share a repository with the other demos in the series (`motion-*`, `newton-*`, `energy-*`, `momentum-*`, `gauss-*`, `circuits-*`, `rc-*`, `magnetism-*`, `induction-*`, `maxwell-*`). The file names don't collide.

## What's inside

The twelve sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Rotational kinematics:** A disk turns with constant angular acceleration. Points at 1, 2 and 3 m trace arcs of length $s=\theta r$, and the page graphs $\theta(t)$ and $\omega(t)$ and shows the right-hand-rule direction of $\vec\omega$.
2. **Linear and angular variables:** For one point on a turning body, the page draws $v=\omega r$, $a_t=\alpha r$, $a_r=\omega^2 r$ and the total acceleration, and reports the period.
3. **Rotational inertia:** Two masses sit on a light rod, and you can move the axis. The page shows $I=\sum m_i r_i^2$, compares the center axis ($\tfrac12 mL^2$) with the end axis ($mL^2$), and gives $K=\tfrac12 I\omega^2$.
4. **Common shapes:** Ten shapes from the textbook table are available, from the hoop to the slab. Each shows its formula and value, and the same torque spins each one up so you can compare how quickly they gain speed. A green curved arrow and vector mark the applied torque (right-hand rule), and a magenta arrow shows the growing angular velocity.
5. **Parallel-axis theorem:** For a rod or a disk, the page plots $I = I_\text{com} + Md^2$ against the offset $d$ and checks it with a numerical $\int r^2\,dm$.
6. **Torque:** A force acts on a lever. The page shows the components $F\cos\varphi$ and $F\sin\varphi$, the lever arm $r\sin\varphi$, and $\vec\tau=\vec r\times\vec F$ with its direction.
7. **Massive pulley:** A block hangs from a pulley that has mass. The page gives $a=\frac{2m}{M+2m}g$, $T=\frac{Mm}{M+2m}g$, and $\alpha=a/R$.
8. **Work and power:** A constant torque spins up a wheel. Energy bars show $W=\tau\theta=\tfrac12 I\omega^2$, the power $P=\tau\omega$ is shown live, and a table pairs each translation quantity with its rotation counterpart.
9. **Rolling:** The page shows the velocity of points on the rim for pure rotation, pure translation, and their sum. In rolling, the top moves at $2v_\text{com}$ and the bottom point P is at rest. It also splits the kinetic energy for a hoop (1 : 1) and a solid disk (1 : 2).
10. **Rolling down a slope:** A sliding block, a sphere, a disk and a hoop race in separate lanes. Each accelerates at $a=\frac{g\sin\theta}{1+I_\text{com}/MR^2}$, the page gives their finishing times, and it shows the static friction on the disk.
11. **Angular momentum:** A spinning person pulls in two dumbbells. $L=I\omega$ stays constant while $\omega$ rises and $K$ changes.
12. **Gyroscope:** A spinning wheel precesses, drawn in 3D with $\vec L$, $\vec\tau$ and $M\vec g$. The page gives $\Omega=\frac{Mgr}{I\omega}$, the time for one precession turn, and the ratio $\omega/\Omega$.

The header animation shows a rolling wheel. At four points on the rim, the velocity is split into the translational part $v_\text{com}$ (green) and the tangential part $\omega R$ (blue), added head to tail to give the total velocity (magenta).

## Notes on the model

- **Animation speed:** Some animations are slowed down so the motion is easy to follow. The readouts always show the real values.
- **Gyroscope:** The wheel is modeled as a uniform disk of radius 0.15 m spinning about its axle. The precession formula assumes $\omega \gg \Omega$.
- **Display:** The pages follow the system's light or dark setting. Under `prefers-reduced-motion`, the continuously spinning displays stand still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
