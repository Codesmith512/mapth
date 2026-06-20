<!-- Custom scroll container to center on screen -->
<div style="position: absolute; top: 0; left: 0; bottom: 0; right: 0; overflow: scroll;" id="image-viewport">
    <!-- img sets size, svg fills it, overlaying links -->
    <div style="position: relative; margin: 0; width: fit-content; height: fit-content;">
        <img style="width: 22in; max-width: none" src="./media/mapth.webp">
        <svg viewBox="0 0 2048 1536" fill="none" xmlns="http://www.w3.org/2000/svg" style="position: absolute; top: 0; right: 0; bottom: 0; left: 0">
            <a href="./topics/naive_set_theory.html">
                <rect opacity="0" x="808" y="653" width="164" height="120" fill="#D9D9D9"/>
            </a>
            <a href="./topics/arithmetic.html">
                <rect opacity="0" x="1162" y="600" width="151" height="116" fill="#D9D9D9"/>
            </a>
        </svg>
    </div>
</div>

<script>
const viewport = document.getElementById('image-viewport');
const img = viewport.querySelectorAll('img')[0]

function centerViewport() {
    viewport.scrollTo(
        (img.width - viewport.clientWidth) / 2,
        (img.height - viewport.clientHeight) / 2,
    );
}

if (img.complete) centerViewport()
else img.addEventListener('load', centerViewport);
</script>

v6 | It's Wargotime ▢