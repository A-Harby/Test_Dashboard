<script>
  import { Doughnut } from "svelte-chartjs";

  export let repo = [];

  export const data = {
    labels: ["Failed", "Passed", "Skipped", "Not run"],
    datasets: [
      {
        data: [repo.Fail, repo.Pass, repo.Skip, repo.Notrun],
        backgroundColor: ["#F7464A", "#8BC34A", "#FDB45C", "#949FB1"],
        hoverBackgroundColor: ["#FF5A5E", "#9CCC4B", "#FFC870", "#A8B3C5"],
      },
    ],
  };

  import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    ArcElement,
    CategoryScale,
    LinearScale,
  } from "chart.js";

  ChartJS.register(
    Title,
    Tooltip,
    Legend,
    ArcElement,
    CategoryScale,
    LinearScale
  );
</script>

<Doughnut {data} options={{ responsive: true }} />
