<script>
  import Sveltree from "./Sveltree.svelte";

  const leaves = [
    {
      title: "My life",
      leaves: [
        {
          title: "Justin Awrey",
          leaves: [
            { title: "Is cool" },
            { title: "Is so cool" },
            { title: "supuer cool" },
            { title: "you dont even know" },
            { title: "Is cool2" },
            { title: "Is so cool4", leaves: [{ title: "who knew" }] },
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
          leaves: [{ title: "SUCKS", leaves: [{ title: "BIG TIME" }] }],
        },
      ],
    },
  ];
</script>

<Sveltree {leaves} />
