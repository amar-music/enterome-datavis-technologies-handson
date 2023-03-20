<script>
    const myRadius = 12
    function myCircle(radius) {
        return Math.round(2*radius*Math.PI).toFixed(2);
    };
</script>

<p>The circumference of a circle with radius {myRadius}m is {myCircle(myRadius)}m </p>