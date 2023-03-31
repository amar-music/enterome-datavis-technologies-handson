<script>
    // Dimensions
    const width = 800;
    const height = 100;
    const margin = { top: 20, right: 20, bottom: 20, left: 20 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    const values = [
      { x: 2, y: 1, category: "cat1" },
      { x: 4, y: 2, category: "cat3" },
      { x: 6, y: 1, category: "cat2" },
      { x: 7, y: 3, category: "cat3" },
      { x: 9, y: 1, category: "cat2" }
    ];

    // Scales
    import { scaleLinear } from "d3-scale";
    const xScale = scaleLinear()
      .domain([2, 9])
      .range([0, innerWidth]);

    const yScale = scaleLinear()
      .domain([1, 3])
      .range([0, innerHeight]);

    import { scaleOrdinal } from "d3-scale";
    const colorScale = scaleOrdinal()
      .domain(["cat1", "cat2", "cat3"])
      .range(["#1f77b4", "#ff7f0e", "#2ca02c"]);


  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">

      {#each values as {x, y, category}}
        <circle cx={xScale(x)} cy={yScale(y)} r="10" fill={colorScale(category)} />
        
        <g class="valueLabel" transform={`translate(${xScale(x)}, ${yScale(y) - 10})`}>
          <text>{y}</text>
        </g>
      {/each}

    </g>
  </svg>
  
  <style>
    text {
      text-anchor: middle;
      font-size: small;
    }
  </style>
  