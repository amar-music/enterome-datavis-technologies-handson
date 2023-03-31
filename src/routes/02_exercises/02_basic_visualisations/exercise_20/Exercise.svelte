<script>
    // Dimensions
    const width = 600;
    const height = 300;
    const margin = { top: 10, right: 10, bottom: 30, left: 60 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    const data = [
      { service: "Netflix", viewers: 2.9 },
      { service: "Amazon Prime Video", viewers: 1.3 },
      { service: "Disney+", viewers: 2.1 },
      { service: "Hulu", viewers: 0.9 },
      { service: "Apple TV", viewers: 1.1 },
      { service: "Rakuten", viewers: 0.4 }
    ];

    const xTicks = data.map(d => d.service);
    const yTicks = [0, 1, 2, 3];

    // Scales
    import { scaleLinear, scaleOrdinal, scaleBand } from "d3-scale";

    const xScale = scaleOrdinal()
      .domain(data.map(d => d.service))
      .range([0, innerWidth]);

    const yScale = scaleLinear()
      .domain([3, 0])
      .range([0, innerHeight]);

    const rScale = scaleBand()
      .domain(data.map(d => d.service))
      .range([0, innerWidth]);


  </script>
  
  <!-- setting a viewBox and max-width allows the SVG to shrink but not grow! -->
  <svg viewbox="0 0 {width} {height}" style="max-width: {width}px">
    <g transform="translate({margin.left} {margin.top})">

      {#each data as {service, viewers}}
        <rect x={rScale(service)} y={yScale(viewers)} width=20 height={yScale(-1)} fill="steelblue" />
      {/each}

      <!-- <rect x={rScale('Netflix')} y={yScale(2.9)} width=20 height={yScale(-1)} />
      <rect x={rScale('Amazon Prime Video')} y={yScale(2.9)} width=20 height={yScale(-1)} />
      <rect x={rScale('Disney+')} y={yScale(2.1)} width=20 height={yScale(-1)} />
      <rect x={rScale('Hulu')} y={yScale(0.9)} width=20 height={yScale(-1)} /> -->

    </g>
  </svg>
  