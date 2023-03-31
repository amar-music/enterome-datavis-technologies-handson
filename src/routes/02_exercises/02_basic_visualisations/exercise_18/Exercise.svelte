<script>
    // Dimensions
    const width = 800;
    const height = 100;
    const margin = { top: 5, right: 5, bottom: 50, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    const values = [2, 4, 6, 7, 9];


    // Scales
    import {extent} from 'd3-array';
    import {scaleLog} from 'd3-scale';
    const scale = scaleLog()
      .domain(extent(values))
      .range([0, innerWidth]);

    import { axisBottom } from 'd3-axis';
    const xAxis = axisBottom()
      .scale(scale);

    //import { select } from 'd3-selection';
      //  select(g).call(xAxis);

  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
      {#each values as value}
        <circle cx={scale(value)} cy={innerHeight/2} r=10 />
      {/each}
    </g>
  </svg>
  