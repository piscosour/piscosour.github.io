---
layout: project-v2
title: Columnista
subtitle: A political column text generation system
shortname: columnista
type: project
date: May 2014
location: Cambridge, MA
permalink: projects/columnista/
featured-image: /files/prensa.jpg
---
{% include project-info-v2.html %}
How do political columns and columnists contribute to informed conversations about government and institutions? In Peru, the fact is that for the most part they don't. In all fairness, there's only so much you can say with only 300 to 500 words - a lot of important detail gets cut, a lot of meaningful nuance has to be left out, and thesis have to be emphasised, if not exaggerated, in the interest of good communication.

All of this, of course, operates at the expense of precisely those elements that would contribute towards strengthening and enriching our democratic conversation. Columnista was built to bring attention to the underlying logics and processes that govern the production of these texts: how could you design a text generation system capable of producing almost limitless permutations of these only apparently significant texts? If an algorithm could produce a sequence of expressions that was plausible enough for an average reader - passing a sort of political column Turing test - what would the implications be for our understanding of political discourse in media in general?

Columnista selects from a pre-defined list of active "issues" discussed in the media and then automatically generates an opinion column commenting on the issue. Of course, the columns generated are not based on research or any actual evaluation, but rather just on a series of familiar tropes and positions that are common to political commentary in Peru. Columnista is an attempt to highlight just how meaningless most political commentary in Peruvian media has become, by providing anyone with a simple tool capable of producing output that is roughly of the same quality.

The design of Columnista was inspired in part by the <a href="http://en.wikipedia.org/wiki/Sokal_affair">Sokal affair</a>, the well-known hoax in which physicist Alan Sokal managed to get a gibberish-based paper published in an important cultural studies journal, to call attention to what were in his view very lax standards for scholarship and academic research. But we also borrowed inspiration from existing text generation systems, such as the <a href="http://www.elsewhere.org/journal/pomo/">PostModern Generator</a> that produce seemingly sensible academic sounding texts with postmodern concepts and language. Columnista is based on a very similar premise to these two examples: if a text can produced that "passes" for a valid text without conforming to any of the standards we would expect from good research, what does that imply for every other similar text?

The first version was a quick 2-3 day programming sprint and it's still fairly limited in functionality. Future development of this code will include a broader ideological registry and more diverse text structures to allow for an even larger set of possible permutations. But the objective is not to be overly explicit about the critique that the algorithm indirectly creates: Columnista calls attention to the problems of an underlying logic by putting said logic into action and bringing it to its inevitable consequences. It is an attempt to evidence the working of that logic, rather than trying to explain it.

<h4>Related:</h4>
<ul>
	<li><a href="http://columnista.mutaciones.pe">Live demo</a></li>
	<li><a href="https://github.com/piscosour/columnista">Code on GitHub</a></li>
</ul>