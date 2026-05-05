---
title: "From AIxCC to OpenSSF: Welcoming OSS-CRS to Advance AI Driven Open Source Security"
url: "https://openssf.org/blog/2026/04/02/from-aixcc-to-openssf-welcoming-oss-crs-to-advance-ai-driven-open-source-security/"
date: "Thu, 02 Apr 2026 14:45:26 +0000"
author: "Jeff Diecks"
feed_url: "https://openssf.org/feed/"
---
<div class="wpb_row vc_row-fluid vc_row" id="fws_69f4ef3056ff5" style="padding-top: 0px; padding-bottom: 0px;"><div class="row-bg-wrap"><div class="inner-wrap row-bg-layer"><div class="row-bg viewport-desktop"></div></div></div><div class="row_col_wrap_12 col span_12 dark left">
	<div class="vc_col-sm-12 wpb_column column_container vc_column_container col no-extra-padding inherit_tablet inherit_phone flex_gap_desktop_10px ">
		<div class="vc_column-inner">
			<div class="wpb_wrapper">
				
<div class="wpb_text_column wpb_content_element ">
	<p><span style="font-weight: 400;">By Jeff Diecks</span></p>
<p><span style="font-weight: 400;">Artificial intelligence is changing how we approach software security. Open source is at the center of that shift.</span></p>
<p><span style="font-weight: 400;">Over the past year, DARPA’s Artificial Intelligence Cyber Challenge (AIxCC) showed that cyber reasoning systems (CRS) can go beyond finding vulnerabilities. These systems can analyze code, confirm issues, and generate patches. This brings us closer to a future where security is more automated and scalable.</span></p>
<p><span style="font-weight: 400;">When the competition ended, one question remained. How do we take these breakthroughs and make them usable in the real world?</span></p>
<p><span style="font-weight: 400;">Today, we are taking an important step forward.</span></p>
<p><span style="font-weight: 400;">The Open Source Security Foundation (OpenSSF) is welcoming </span><b>OSS-CRS</b><span style="font-weight: 400;"> as a new open source project under the AI / ML Security Working Group.</span></p>
<p><span style="font-weight: 400;">OSS-CRS emerged from AIxCC and is a standard orchestration framework for building and running LLM-based autonomous bug-finding and bug-fixing systems.</span></p>
<p><span style="font-weight: 400;">The open framework is designed to make CRS practical outside of the AIxCC environment. During the competition, teams built powerful systems that were released as open source. However, many of them depended on the competition infrastructure, which made them difficult to reuse or extend. OSS-CRS addresses that gap.</span></p>
<p><span style="font-weight: 400;">OSS-CRS Features include:</span></p>
<ul>
<li style="font-weight: 400;"><b>Standard CRS Interface:</b><span style="font-weight: 400;"> OSS-CRS defines a unified interface for CRS development. Build your CRS once following the development guide, and run it across different environments (local, Azure, …) without any modification.</span></li>
<li style="font-weight: 400;"><b>Effortless Targeting:</b><span style="font-weight: 400;"> Run any CRS against projects in OSS-Fuzz format. If your project is compatible with OSS-Fuzz, OSS-CRS can orchestrate CRSs against it out of the box.</span></li>
<li style="font-weight: 400;"><b>Ensemble Multiple CRSs:</b><span style="font-weight: 400;"> Compose and run multiple CRSs together in a single campaign to combine their strengths and maximize bug-finding and bug-fixing coverage.</span></li>
<li style="font-weight: 400;"><b>Resource Control:</b><span style="font-weight: 400;"> Manage CPU limits and LLM budgets per CRS to keep costs and resources in check.</span></li>
</ul>
<p><span style="font-weight: 400;">Read the OSS-CRS research paper:</span><a href="https://doi.org/10.48550/arXiv.2603.08566"> <span style="font-weight: 400;">https://doi.org/10.48550/arXiv.2603.08566</span></a></p>
<h2><b>From Competition to Community</b></h2>
<p><span style="font-weight: 400;">The move of OSS-CRS into OpenSSF marks a clear transition from research and competition to open collaboration and long term development.</span></p>
<p><span style="font-weight: 400;">OpenSSF provides a neutral home where projects like OSS-CRS can grow. Contributors can work together to improve the tools, validate results, and support adoption across the ecosystem.</span></p>
<p><span style="font-weight: 400;">OSS-CRS is already producing real results. Using OSS-CRS, Team Atlanta discovered twenty-five vulnerabilities across sixteen projects spanning a broad range of software including PHP, U-Boot, memcached, and Apache Ignite 3.</span></p>
<p><span style="font-weight: 400;">OpenSSF will continue to support this important work by providing human connectors between CRS tools and open source communities. The goal is to help triage and validate vulnerability reports and proposed patches before they reach maintainers, ensuring findings are accurate, actionable, and respectful of maintainers&#8217; time.</span></p>
<p><a href="https://team-atlanta.github.io/blog/post-patch-2026-ensemble/"><span style="font-weight: 400;">Recent research from the OSS-CRS team</span></a><span style="font-weight: 400;"> validates the necessity of having a human in the loop. The team manually reviewed a set of 630 AI-generated patches and found 20-40% of the patches to be semantically incorrect. The incorrect patches pass all automated validation but are actually wrong — a dangerous failure mode only catchable by manual review.</span></p>
<p><span style="font-weight: 400;">A key benefit of the OSS-CRS project is its Ensemble feature. The Ensemble feature enhances accuracy and reliability by combining patches from multiple CRS approaches and using a selection process to pick the one most likely to be correct. The research showed this approach consistently matches or outperforms the best single component in improving semantic correctness, which is hard to eliminate at the single-agent level. This collaboration of systems helps produce more robust results for open source defenders.</span></p>
<h2><b>Get Involved</b></h2>
<p><span style="font-weight: 400;">With projects like OSS-CRS, OpenSSF will continue to support AI-driven security work to help turn innovation into practical outcomes for open source.</span></p>
<p><span style="font-weight: 400;">We offer several options to get involved including:</span></p>
<ul>
<li style="font-weight: 400;"><a href="https://openssf.org/projects/oss-crs/"><span style="font-weight: 400;">Explore the OSS-CRS Project</span></a></li>
<li style="font-weight: 400;"><a href="https://openssf.org/groups/ai-ml-security/"><span style="font-weight: 400;">Join the AI / ML Security Working Group</span></a></li>
<li style="font-weight: 400;"><a href="https://github.com/ossf/ai-ml-security?tab=readme-ov-file#projects"><span style="font-weight: 400;">Join the Cyber Reasoning Systems Special Interest Group</span></a></li>
</ul>
<h3><span style="font-weight: 400;">Author Bio</span></h3>
<p><span style="font-weight: 400;"><img alt="" class="alignleft wp-image-10694 size-thumbnail" height="150" src="https://openssf.org/wp-content/uploads/2026/03/Screenshot-2024-08-28-at-11.54.36-AM-3-150x150.png" width="150" />Jeff Diecks is a Senior Technical Program Manager at The Linux Foundation. He has more than two decades of experience in technology and communications with a diverse background in operations, project management and executive leadership. A participant in open source since 1999, he’s delivered digital products and applications for universities, sports leagues, state governments, global media companies and non-profits.</span></p>
</div>




			</div> 
		</div>
	</div> 
</div></div>
