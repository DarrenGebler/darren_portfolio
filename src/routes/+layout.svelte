<script>
    function handleMousemove(event) {
        const mouseX = event.clientX;
        const mouseY = event.clientY;

        const anchor = document.getElementById('anchor');
        const rekt = anchor.getBoundingClientRect();
        const anchorX = rekt.left + rekt.width / 2;
        const anchorY = rekt.top + rekt.height / 2;


        const angleDeg = angle(mouseX, mouseY, anchorX, anchorY);

        const eyes = document.querySelectorAll('.eye');
        eyes.forEach(eye => {
            eye.style.transform = `rotate(${90 + angleDeg}deg)`;
        })
    }

    function angle(cx, cy, ex, ey) {
        const dy = ey - cy;
        const dx = ex - cx;
        const rad = Math.atan2(dy, dx);
        return rad * 180 / Math.PI;
    }
</script>

<div class="app" on:mousemove={handleMousemove}>
    <main>
        <slot/>
    </main>
</div>

<style>
    @import url('https://fonts.googleapis.com/css?family=Poppins:300,400,500,600,700,800,900&display=swap');
    .app {
        background-color: #ECE5DD;
        font-family: 'Poppins', sans-serif;
        padding: 0;
        margin: 0;
    }
</style>