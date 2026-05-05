---
title: "OpenSSF Tech Talk Recap: Securing Agentic AI"
url: "https://openssf.org/blog/2026/04/08/openssf-tech-talk-recap-securing-agentic-ai/"
date: "Wed, 08 Apr 2026 20:13:25 +0000"
author: "OpenSSF"
feed_url: "https://openssf.org/feed/"
---
<p><span style="font-weight: 400;">The shift from traditional software to agentic Artificial Intelligence (AI) represents a fundamental change in the security landscape. While traditional systems are deterministic, AI agents are non-deterministic by design. This presents a new set of challenges: execution paths that change with the same input, runtime discovery of access surfaces, and the critical need for delegated identity.</span></p>
<p><span style="font-weight: 400;">At our recent </span><a href="http://openssf.org"><span style="font-weight: 400;">Open Source Security Foundation (OpenSSF)</span></a><span style="font-weight: 400;"> Tech Talk, experts from Microsoft, Thread AI, Canonical, and the OpenSSF AI/ML Security Working Group joined forces to dismantle the &#8220;black box&#8221; of AI security. They provided a roadmap for securing the entire stack – from the user prompt down to the silicon. For those who missed the live session, the </span><a href="https://youtu.be/4NRdBszVPqA?si=N0yHtjBDGK2DJ2D8"><b>full recording</b></a><b> and </b><a href="https://openssf.org/resources/tech-talks/tech-talk-securing-agentic-ai-in-practice-from-openssf-guidance-to-real-world-implementation/"><b>slide deck</b></a><b> are now available</b><span style="font-weight: 400;"> on demand.</span></p>
<h2><span style="font-weight: 400;">The New Threat Model: Why Agents Differ</span></h2>
<p><span style="font-weight: 400;">Angela McNeal of Thread AI opened the discussion by highlighting why our existing frameworks need a major upgrade. &#8220;Traditional software processes are deterministic,&#8221; McNeal noted. &#8220;AI agents, however, follow the path of least resistance.&#8221;</span></p>
<p><span style="font-weight: 400;">Without explicit boundaries, an agent might pull records for an entire family plan just to process a single claim. This occurs not out of malice, but from a drive to be thorough. This &#8220;unbounded&#8221; nature makes least privilege an architectural requirement rather than a mere policy.</span></p>
<h3><span style="font-weight: 400;">Key Problem Areas:</span></h3>
<ul>
<li style="font-weight: 400;"><b>Agent Autonomy:</b><span style="font-weight: 400;"> The risk of &#8220;confused deputy&#8221; problems where agents delegate tasks to sub-agents without narrowing authorization scopes.</span></li>
<li style="font-weight: 400;"><b>Tool-Model Trust:</b><span style="font-weight: 400;"> Every Application Programming Interface (API) and the Model Context Protocol (MCP) server is an untrusted boundary. Models cannot natively distinguish between data and instructions, a vulnerability known as prompt injection.</span></li>
<li style="font-weight: 400;"><b>Context Integrity:</b><span style="font-weight: 400;"> Decision-making must be defensible. Organizations must capture the &#8220;reasoning chain&#8221; of an agent to satisfy regulators. Logging only the final output is insufficient.</span></li>
</ul>
<h2><span style="font-weight: 400;">Introducing SAFE-MCP: A Threat Catalog for the AI Era</span></h2>
<p><span style="font-weight: 400;">To address these vulnerabilities, Frederick Kautz, contributor of the OpenSSF AI/ML Security Working Group introduced SAFE-MCP, one of the newest initiatives and SIGs within the OpenSSF. Inspired by the MITRE ATT&amp;CK® framework, SAFE-MCP provides a standardized catalog of over 80 attack techniques specifically targeting tool-based Large Language Models (LLMs).</span></p>
<p><span style="font-weight: 400;">&#8220;The attacks often live within the changes of assumptions,&#8221; Kautz explained. &#8220;If we just do what we did two years ago, we are going to open ourselves up to attacks.&#8221;</span></p>
<p><span style="font-weight: 400;">By assigning specific identifiers to threats, such as SAFE-T1201 (MCP Rugpull Attack) – the community can communicate without ambiguity. This allows security teams to verify whether their architecture successfully mitigates specific, known risks such as context exfiltration or lateral movement.</span></p>
<h2><span style="font-weight: 400;">The &#8220;Seven-Layer Cake&#8221; of AI Infrastructure</span></h2>
<p><span style="font-weight: 400;">Hugo Huang and Abdelrahman Hosny of Canonical shifted the focus to the underlying infrastructure. They described AI security as a seven-layer stack, emphasizing that open source is the bedrock of every layer.</span></p>
<ol>
<li style="font-weight: 400;"><b>User Interface:</b><span style="font-weight: 400;"> Web applications with thousands of open source dependencies.</span></li>
<li style="font-weight: 400;"><b>Orchestration:</b><span style="font-weight: 400;"> Tools such as Ollama or vLLM that manage model loading and memory.</span></li>
<li style="font-weight: 400;"><b>Inference Runtime:</b><span style="font-weight: 400;"> The math engine (e.g., Llama.cpp) that executes matrix multiplications.</span></li>
<li style="font-weight: 400;"><b>Model Format:</b><span style="font-weight: 400;"> Static files that can be poisoned to corrupt the sampling process.</span></li>
<li style="font-weight: 400;"><b>Hardware Drivers:</b><span style="font-weight: 400;"> The software communicating with the Graphics Processing Unit (GPU) or Language Processing Unit (LPU).</span></li>
<li style="font-weight: 400;"><b>Kernel:</b><span style="font-weight: 400;"> The Linux bedrock managing resource allocation.</span></li>
<li style="font-weight: 400;"><b>Silicon:</b><span style="font-weight: 400;"> The physical hardware (NVIDIA, Intel, AMD) that provides high-performance computing power.</span></li>
</ol>
<p><span style="font-weight: 400;">With more than 3,000 open source dependencies in a typical AI stack, the panel stressed the importance of Software Bill of Materials (SBOM) visibility and enterprise-grade patch management.</span></p>
<h2><span style="font-weight: 400;">How to Get Involved</span></h2>
<p><span style="font-weight: 400;">Securing the future of open source AI is a community-wide effort. The OpenSSF provides several resources for organizations to maintain security:</span></p>
<ul>
<li style="font-weight: 400;"><b>Watch the Session:</b><span style="font-weight: 400;"> Access the </span><a href="https://youtu.be/4NRdBszVPqA?si=N0yHtjBDGK2DJ2D8"><span style="font-weight: 400;">recording</span></a><span style="font-weight: 400;"> and download the </span><a href="https://openssf.org/resources/tech-talks/tech-talk-securing-agentic-ai-in-practice-from-openssf-guidance-to-real-world-implementation/"><span style="font-weight: 400;">presentation slides</span></a><span style="font-weight: 400;">.</span></li>
<li style="font-weight: 400;"><b>Take the Course:</b><span style="font-weight: 400;"> Enroll in our free express learning course, </span><a href="https://training.linuxfoundation.org/express-learning/secure-ai-ml-driven-software-development-lfel1012/"><span style="font-weight: 400;">Secure AI/ML-Driven Software Development (LFEL1012)</span></a><span style="font-weight: 400;"> and earn a digital badge.</span></li>
<li style="font-weight: 400;"><b>Join the Working Group:</b><span style="font-weight: 400;"> Participate in the </span><a href="https://openssf.org/technical-initiatives/ai-ml-security/"><span style="font-weight: 400;">AI/ML Security Working Group</span></a><span style="font-weight: 400;"> to help shape these emerging standards.</span></li>
<li style="font-weight: 400;"><b>Contribute to SAFE-MCP:</b><span style="font-weight: 400;"> Visit the </span><a href="https://github.com/safe-agentic-framework/safe-mcp"><span style="font-weight: 400;">SAFE-MCP repository</span></a><span style="font-weight: 400;"> for sharing feedback or contributing new threat techniques.</span></li>
</ul>
