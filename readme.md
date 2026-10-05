<!-- Custom styling for the below SVG -->
<style>
a[href] > rect {
    opacity: 0;
}
</style>

<!-- Custom scroll container to center on screen -->
<div style="position: absolute; top: 0; left: 0; bottom: 0; right: 0; overflow: scroll;" id="image-viewport">
    <!-- img sets size, svg fills it, overlaying links -->
    <div style="position: relative; margin: 0; width: fit-content; height: fit-content;">
        <img style="width: 22in; max-width: none" src="./media/mapth.webp">
        <svg viewBox="0 0 4096 3072" fill="none" xmlns="http://www.w3.org/2000/svg" style="position: absolute; top: 0; right: 0; bottom: 0; left: 0">
            <a href="./topics/logic_zero_order.html"> <rect opacity="0.5" x="1141" y="905" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="611" y="1437" width="391" height="231" fill="#CC2288"/> </a>
            <a href="./topics/logic_first_order.html"> <rect opacity="0.5" x="1192" y="1437" width="397" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="763" y="1783" width="391" height="231" fill="#CC2288"/> </a>
            <a href="./topics/logic_higher_order.html"> <rect opacity="0.5" x="1171" y="1668" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="1171" y="2118" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="457" y="2173" width="478" height="317" fill="#CC2288"/> </a>
            <a href="./topics/problem_pvnp.html"> <rect opacity="0.5" x="810" y="889" width="293" height="317" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="1589" y="2160" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="1318" y="2434" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="2418" y="2233" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="1629" y="1863" width="391" height="231" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="1629" y="1566" width="391" height="231" fill="#CC2288"/> </a>
            <a href="./topics/naive_set_theory.html"> <rect opacity="0.5" x="1668" y="1269" width="391" height="231" fill="#CC2288"/> </a>
            <a href="./topics/arithmetic.html"> <rect opacity="0.5" x="2350" y="1206" width="391" height="231" fill="#CC2288"/> </a>
            <a href="./topics/route01.html"> <rect opacity="0.5" x="2059" y="1233" width="291" height="109" fill="#CC2288"/> </a>
            <a> <rect opacity="0.5" x="2399" y="1517" width="391" height="231" fill="#CC2288"/> </a>
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

v6 | [It's Wargotime ▢](https://wargotime.com)