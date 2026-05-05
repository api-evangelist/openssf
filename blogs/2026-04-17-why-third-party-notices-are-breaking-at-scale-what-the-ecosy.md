---
title: "Why Third-Party Notices Are Breaking at Scale: What the Ecosystem Needs Next"
url: "https://openssf.org/blog/2026/04/17/why-third-party-notices-are-breaking-at-scale-what-the-ecosystem-needs-next/"
date: "Fri, 17 Apr 2026 13:44:55 +0000"
author: "OpenSSF"
feed_url: "https://openssf.org/feed/"
---
<div class="wpb_row vc_row-fluid vc_row" id="fws_69f4ef304e05e" style="padding-top: 0px; padding-bottom: 0px;"><div class="row-bg-wrap"><div class="inner-wrap row-bg-layer"><div class="row-bg viewport-desktop"></div></div></div><div class="row_col_wrap_12 col span_12 dark left">
	<div class="vc_col-sm-12 wpb_column column_container vc_column_container col no-extra-padding inherit_tablet inherit_phone flex_gap_desktop_10px ">
		<div class="vc_column-inner">
			<div class="wpb_wrapper">
				
<div class="wpb_text_column wpb_content_element ">
	<p>By Devashri Datta, Independent Researcher, Software Supply Chain Security</p>
<p><span style="font-weight: 400;">Third-party notices (TPNs) are documents distributed to users that list open source third-party software components included in the product and key licensing information. Every time you buy a TV or router, you’ve probably seen them. Yet TPNs were never designed for the complexity, scale, and velocity of today’s software ecosystem. TPNs are one of the most widely distributed and yet least understood artifacts in modern software supply chains.</span></p>
<p><span style="font-weight: 400;">Inside nearly every appliance, firmware image, SaaS platform, and enterprise distribution, the same pattern persists: a long, unstructured PDF is expected to represent the full scope of open source license compliance.</span></p>
<p><span style="font-weight: 400;">As software systems have scaled, TPNs have quietly become a critical but increasingly fragile pillar. They are now failing technically, operationally, and structurally under the demands of modern development and distribution.</span></p>
<p><span style="font-weight: 400;">This article examines why TPNs are breaking. It also outlines what the ecosystem must do next based on large-scale analysis of real-world TPN documents and the development of an automated framework for extracting information directly from them. While traditionally viewed as compliance artifacts, Third-Party Notices (TPNs) also represent an underutilized source of security-relevant intelligence. In many real-world scenarios where Software Bills of Materials (SBOMs) are incomplete, unavailable, or restricted, TPNs may provide the only observable evidence of component usage. This positions TPNs as a critical input to software supply chain security workflows, including vulnerability management, third-party risk assessment, and incident response.</span></p>
<h2><span style="font-weight: 400;">The Hidden Reality: TPNs Are the Supply Chain’s Last Mile</span></h2>
<p><span style="font-weight: 400;">Despite advances in Software Bill of Materials (SBOM) formats such as SPDX and CycloneDX, TPNs remain:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">The only compliance artifact that many vendors publicly distribute</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">The only artifact available to customers or regulators for proprietary systems</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">The only verifiable attribution record when source code and SBOMs are inaccessible</span></li>
</ul>
<p><span style="font-weight: 400;">SBOMs provide structured visibility into software components, but their completeness depends on the generation methods and the availability of build-time data. In practice, SBOMs may not consistently capture full transitive dependencies or runtime-resolved components. In some cases, additional components and licensing details may appear in downstream artifacts such as third-party notices (TPNs), though these are typically not integrated into SBOM analysis pipelines. SBOM availability also varies across organizations and products and may not always be accessible to end users or external stakeholders due to policy or regulatory interpretation. Regulatory frameworks such as the </span><a href="https://eur-lex.europa.eu/eli/reg/2024/2847/oj/eng"><span style="font-weight: 400;">EU Cyber Resilience Act (CRA)</span></a><span style="font-weight: 400;"> are evolving, and expectations around SBOM scope and disclosure remain subject to interpretation. As a result, relying solely on SBOM data may not provide complete visibility into whether a product contains a specific vulnerable component, depending on SBOM completeness and related artifact availability.</span></p>
<p><span style="font-weight: 400;">In practice, TPNs often serve as the last mile of compliance visibility, bridging internal software composition and external disclosure.</span></p>
<p><span style="font-weight: 400;">However, TPNs were never designed to operate at the scale or complexity of today’s supply chains.</span></p>
<h2><span style="font-weight: 400;">Security Blind Spot in Software Supply Chains</span></h2>
<p><span style="font-weight: 400;">While SBOMs and software composition analysis (SCA) tools have improved visibility during development, they assume access to structured or source level data. In contrast, TPNs often represent the only externally available artifact in downstream consumption environments such as embedded systems, firmware, and proprietary SaaS distributions.</span></p>
<p><span style="font-weight: 400;">This creates a structural blind spot in software supply chain security: security teams are frequently forced to make risk decisions without machine readable component intelligence. As a result, vulnerability exposure, dependency risk, and third-party software usage often remain partially or completely unobservable at the point of consumption.</span></p>
<h2><span style="font-weight: 400;">Why the TPN Ecosystem Is Breaking</span></h2>
<h3><span style="font-weight: 400;">PDFs Are an Anti-Pattern for Machine-Readable Compliance</span></h3>
<p><span style="font-weight: 400;">Most TPNs are distributed as large, heterogeneous PDFs containing:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Multi-column layouts</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">OCR artifacts and noise</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Inconsistent license formatting</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Duplicated or truncated license text</span></li>
</ul>
<p><span style="font-weight: 400;">TPNs often omit component identifiers and lack specific version numbers for components.</span></p>
<p><span style="font-weight: 400;">PDFs are optimized for display, not structured data. As a result, extracting meaningful compliance information programmatically is extremely difficult.</span></p>
<h3><span style="font-weight: 400;">Existing Compliance Tools Don’t Address the Problem</span></h3>
<p><span style="font-weight: 400;">Current tools such as FOSSology, ScanCode, and ORT are designed to analyze source code or binaries—not TPN documents. Yet in many real-world scenarios, especially audits or vendor reviews, TPNs are the only artifact available.</span></p>
<p><span style="font-weight: 400;">This creates a fundamental gap: The most widely distributed compliance artifact is the least analyzable.</span></p>
<h3><span style="font-weight: 400;">Inconsistent Generation Pipelines Lead to Data Drift</span></h3>
<p><span style="font-weight: 400;">TPNs are generated through highly variable processes:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Custom scripts</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Proprietary internal tooling</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Manual aggregation from legacy systems</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Partial or outdated SBOM exports</span></li>
</ul>
<p><span style="font-weight: 400;">As a result, even TPNs from the same organization can vary significantly across releases, introducing inconsistencies, omissions, and misalignment with actual dependencies.</span></p>
<h3><span style="font-weight: 400;">Scale Has Outpaced Human Review</span></h3>
<p><span style="font-weight: 400;">Modern TPNs often span hundreds of pages across multiple license families and components.</span></p>
<p><span style="font-weight: 400;">Manual review has become increasingly impractical due to:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Repetitive license text</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Poorly structured component mappings</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Lack of contextual metadata</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Hidden obligations within large text blocks</span></li>
</ul>
<p><span style="font-weight: 400;">Compliance teams are effectively being asked to analyze documents at a scale that exceeds human capability.</span></p>
<h2><span style="font-weight: 400;">Proposed Contribution: TPN-to-Security Intelligence Framework</span></h2>
<p><span style="font-weight: 400;">This work introduces a systematic framework for transforming Third-Party Notices (TPNs) from unstructured compliance artifacts into structured security intelligence inputs. The framework addresses a critical gap in software supply chain security: the absence of machine-readable component visibility in downstream and vendor-distributed environments.</span></p>
<p><span style="font-weight: 400;">Unlike traditional software composition analysis tools that rely on source code, build artifacts, or SBOMs, this approach operates on TPNs as a primary data source. It enables the extraction, classification, and interpretation of software components and license obligations from highly unstructured documents.</span></p>
<p><span style="font-weight: 400;">The key contribution of this work is the demonstration that TPNs can be operationalized into actionable security intelligence for:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Vulnerability exposure identification when SBOMs are unavailable</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Third-party risk assessment using externally visible artifacts</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Incident response prioritization based on inferred component usage</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Governance and compliance enforcement through structured outputs</span></li>
</ul>
<h2><span style="font-weight: 400;">Breaking the Logjam: Toward Automated License Intelligence</span></h2>
<p><span style="font-weight: 400;">To address this systemic gap, I developed an automated end-to-end framework that treats TPNs as primary compliance artifacts, rather than secondary documentation.</span></p>
<p><span style="font-weight: 400;">The approach enables structured extraction and interpretation of license intelligence directly from unstructured documents. While TPNs may lack some information, they still provide valuable signals. For example, even without version identifiers, knowing that a product includes a component can be very valuable (e.g., when asking “which products contain a version of log4j that might be vulnerable to this attack?”).</span></p>
<h2><span style="font-weight: 400;">Structured Extraction from Unstructured PDFs</span></h2>
<p><span style="font-weight: 400;">Using normalization, segmentation, and page-level reconstruction, the system identifies and extracts coherent license blocks even from highly inconsistent documents.</span></p>
<h2><span style="font-weight: 400;">License Identification and Classification</span></h2>
<p><span style="font-weight: 400;">A hybrid approach combining rule-based methods and fuzzy matching maps extracted text into meaningful license categories:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Permissive</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Weak copyleft</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Strong copyleft</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Proprietary</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Public domain</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Content licenses</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Unknown</span></li>
</ul>
<p><span style="font-weight: 400;">This approach achieves, in my testing:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">92–96% accuracy for permissive licenses</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">85–90% accuracy for copyleft detection</span></li>
</ul>
<h2><span style="font-weight: 400;">Risk Interpretation</span></h2>
<p><span style="font-weight: 400;">Each component is evaluated for compliance risk based on obligations such as:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Attribution requirements</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Redistribution conditions</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Copyleft scope</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Source disclosure obligations</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Ambiguous or unidentified licenses</span></li>
</ul>
<h2><span style="font-weight: 400;">Visualization and Machine-Readable Outputs</span></h2>
<p><span style="font-weight: 400;">The framework produces:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Interactive dashboards</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Structured datasets</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Outputs compatible with governance workflows and SBOM pipelines</span></li>
</ul>
<p><span style="font-weight: 400;">This demonstrates that meaningful compliance intelligence can be derived even from the most constrained artifact available. This closes a long-standing visibility gap in the software supply chain.</span></p>
<p><span style="font-weight: 400;">Security Implications of TPN Breakdown</span></p>
<p><span style="font-weight: 400;">The failure of TPNs is not only a compliance problem—it has direct consequences for software supply chain security. When TPNs are inconsistent, unstructured, or incomplete, they reduce the ability of downstream stakeholders to:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Identify exposure to known vulnerable components</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Trace dependency relationships in third-party software</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Perform accurate third-party risk assessments</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Respond quickly to emerging vulnerabilities in production systems</span></li>
</ul>
<p><span style="font-weight: 400;">This makes TPN degradation a security visibility problem, not just a documentation inefficiency.</span></p>
<h2><span style="font-weight: 400;">What the Ecosystem Needs Next</span></h2>
<p><span style="font-weight: 400;">TPN failures are not isolated inefficiencies. They represent a structural weakness in how the global software supply chain communicates compliance.</span></p>
<p><span style="font-weight: 400;">Addressing this requires coordinated effort across standards, tooling, and ecosystem alignment.</span></p>
<h2><span style="font-weight: 400;">Standardized, Machine-Readable TPN Formats</span></h2>
<p><span style="font-weight: 400;">The ecosystem needs formats beyond PDFs, such as:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Creating a standard TPN-JSON format for use</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">SPDX-aligned TPN profiles</span></li>
</ul>
<p><span style="font-weight: 400;">These would enable structured, interoperable compliance disclosures.</span></p>
<p><span style="font-weight: 400;">One possible longer-term solution is to embed machine-readable data (such as an SBOM in SPDX format or a TPN in JSON format) within the PDFs, creating a “hybrid PDF”. The PDF format already permits adding internal files (called “attached files”). LibreOffice already supports generating PDFs that embed the source document, allowing people to use their existing process for exchanging display PDF while also including machine-readable data. Tools that can quickly extract those embedded files and complain when they’re not present could speed their deployment. However, while this approach has promise, it doesn’t deal with the current documents, which do not embed this information.</span></p>
<h2><span style="font-weight: 400;">Improved Support for Dependency Analysis</span></h2>
<p><span style="font-weight: 400;">Unsurprisingly, many improvements for handling dependencies could help in processing TPNs, SBOMs, and many other related formats.</span></p>
<p><span style="font-weight: 400;">It would be better if there was shared reference corpora for license matching. That’s because accurate license detection requires:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Canonical license datasets</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Variant and legacy license mappings</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Community-maintained reference corpora</span></li>
</ul>
<p><span style="font-weight: 400;">This would significantly improve consistency across tools and organizations.</span></p>
<p><span style="font-weight: 400;">In addition, there should be open APIs for information on licensing. Standard APIs should support:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">License extraction</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Component-to-license mapping</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Obligation and risk interpretation</span></li>
</ul>
<p><span style="font-weight: 400;">This would enable interoperability between vendors, auditors, and regulators.</span></p>
<h2><span style="font-weight: 400;">Integration Between SBOM and TPN Pipelines</span></h2>
<p><span style="font-weight: 400;">Today, SBOMs and TPNs exist in disconnected workflows. Yet in many cases, TPNs provide the only information available about product components.</span></p>
<p><span style="font-weight: 400;">A unified pipeline would:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Eliminate duplication</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Reduce inconsistencies</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Ensure alignment between internal and external disclosures</span></li>
</ul>
<h2><span style="font-weight: 400;">Related Work</span></h2>
<p><span style="font-weight: 400;">Prior efforts across the software supply chain ecosystem have focused on improving license detection and SBOM generation during development and build phases. However, these approaches often assume access to source code or structured metadata, leaving a visibility gap when Third‑Party Notices (TPNs) are the only available compliance artifact.</span></p>
<p><span style="font-weight: 400;">Related work on automating TPN analysis demonstrates how unstructured compliance documents can be transformed into machine‑readable license intelligence suitable for governance and audit workflows. Supporting datasets for compliance governance and SBOM alignment are described in:</span></p>
<p><span style="font-weight: 400;">Datta, D., **TPN Compliance Dataset for Software Supply Chain Governance**, Zenodo, 2025. </span></p>
<p><a href="https://doi.org/10.5281/zenodo.19152619"><span style="font-weight: 400;">https://doi.org/10.5281/zenodo.19152619</span></a></p>
<p><span style="font-weight: 400;">Framework:</span></p>
<p><a href="https://doi.org/10.5281/zenodo.19099831"><span style="font-weight: 400;">https://doi.org/10.5281/zenodo.19099831</span></a></p>
<h2><span style="font-weight: 400;">Security Workflow Integration Model</span></h2>
<p><span style="font-weight: 400;">The proposed framework reframes TPNs as an input layer in modern software supply chain security workflows. Rather than treating TPNs as static compliance documentation, they can be operationalized into structured security intelligence pipelines.</span></p>
<p><span style="font-weight: 400;">The extracted data can be integrated into:</span></p>
<ul>
<li style="font-weight: 400;"><span style="font-weight: 400;">Vulnerability management systems (to identify exposed components when SBOMs are missing)</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Third-party risk management (TPRM) platforms (to assess supplier software risk)</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">Incident response workflows (to rapidly evaluate exposure after CVE disclosures)</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">DevSecOps pipelines (to enforce policy-based controls on software composition)</span></li>
</ul>
<p><span style="font-weight: 400;">This positions TPN analysis as a bridge between compliance documentation and operational security decision-making.</span></p>
<h2><span style="font-weight: 400;">Conclusion: The Future Requires Fixing TPNs</span></h2>
<p><span style="font-weight: 400;">Third-party notices (TPNs) were originally designed as simple attribution mechanisms and ways to declare licenses to recipients (as required by many licenses). Today, they are expected to support audits, transparency, regulatory compliance, and supply chain security.</span></p>
<p><span style="font-weight: 400;">But they are still delivered as static documents that do not scale.</span></p>
<p><span style="font-weight: 400;">TPNs are not failing because organizations lack intent; they are failing because the ecosystem has outgrown the tools and formats upon which it relies.</span></p>
<p><span style="font-weight: 400;">If we want a more transparent, auditable, and trustworthy software supply chain, TPNs must evolve into structured, machine-readable, and interoperable artifacts.</span></p>
<p><span style="font-weight: 400;">The next phase of open source security will not be defined solely by SBOMs or scanning tools, but by how effectively we solve the last mile of compliance visibility.</span></p>
<p><span style="font-weight: 400;">Fixing TPNs is an important step toward a more reliable and verifiable software ecosystem.</span></p>
<p>&nbsp;</p>
<p><span style="font-weight: 400;">Acknowledgments</span></p>
<p><span style="font-weight: 400;">The author acknowledges David A. Wheeler and Sally Cooper for their insightful feedback and helpful discussions during the development of this work.</span></p>
<h2><span style="font-weight: 400;">Resources</span></h2>
<p><span style="font-weight: 400;">The open source implementation of the prototype described in this post, including parsing logic, license-classification rules, and the interactive dashboard, is available on GitHub for anyone interested in exploring or extending the approach:</span></p>
<p><a href="https://github.com/devashridatta-dotcom/tpn-automation"><span style="font-weight: 400;">https://github.com/devashridatta-dotcom/tpn-automation</span></a></p>
<p><span style="font-weight: 400;">Community feedback and contributions are welcome.</span></p>
<h3><span style="font-weight: 400;">Author Bio</span></h3>
<p><span style="font-weight: 400;"><img alt="" class="alignleft wp-image-10849 size-thumbnail" height="150" src="https://openssf.org/wp-content/uploads/2026/04/devashri-150x150.jpeg" width="150" />Devashri Datta is an AI &amp; Software Supply Chain Security Researcher. Security researcher and enterprise security architect focused on software supply chain security, DevSecOps automation, and security governance at scale. Research areas include SBOM governance, vulnerability intelligence (VEX), Third-Party Notice (TPN) analysis, AI-assisted risk modeling, and security exception management in cloud-native environments under compliance frameworks such as SOC 2, ISO 27001, and FedRAMP.</span></p>
</div>




			</div> 
		</div>
	</div> 
</div></div>
