<script>
  import Sveltree from "./Sveltree.svelte";

  const nodes = [
    {
      title: "My life",
      nodes: [
        {
          title: "Justin Awrey",
          nodes: [
            { title: "Is cool" },
            { title: "Is so cool" },
            { title: "supuer cool" },
            { title: "you dont even know" },
            { title: "Is cool2" },
            { title: "Is so cool4", nodes: [{ title: "who knew" }] },
            { title: "supuer cool9" },
            { title: "you dont even 9know" },
            { title: "Is coo1l" },
            { title: "Is so 1cool" },
            { title: "supuer -cool" },
            { title: "you don0t even know" },
          ],
        },
        {
          title: "Paulina Buskas",
          nodes: [{ title: "SUCKS", nodes: [{ title: "BIG TIME" }] }],
        },
      ],
    },
  ];
</script>

<Sveltree {nodes} />
