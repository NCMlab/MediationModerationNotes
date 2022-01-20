# Render Mediation-Moderation Setup File
Permanent Note
Created: 01-19-2022 09:08

The setup file for mediation/moderation analyses should generate HTML of the models. These allow the user to setup a model and then to visually check to make sure it is what is expected.


Need: mermaid rendering for display in HTML.

`<html>
<head>
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
<script>
mermaid.initialize({startOnLoad:true});
</script>
<style>
    .mermaid {  /* add custom styling */  }
</style>
</head>
<body>
<div class="mermaid">
graph LR
	A-->B;
	B-->C;
	A-->C;
</div>
</body>
</html>
`

## References
1. 