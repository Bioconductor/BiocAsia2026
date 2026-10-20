+++
title = "Schedule"
description = "Schedule"
+++

BioC Asia 2026 runs alongside the ABACBS workshops. BioC Asia sessions are listed first in each time slot. Click a column heading to sort, or use the filters to narrow the list.

<a class="cta-button" href="https://www.abacbs.org/workshops-2026-call" target="_blank" rel="noopener">Register Now</a>

See the [Registration](/registration/) page for prices and options.

⭐ = Workshop spans the entire morning or afternoon, including both sessions and the break.

<style>
.sched-filters { display: flex; flex-wrap: wrap; gap: 10px 16px; align-items: flex-end; margin: 20px 0 12px; }
.sched-filters label { display: flex; flex-direction: column; font-weight: 600; font-size: 13px; margin: 0; }
.sched-filters select, .sched-filters input[type=search] { font-weight: normal; margin-top: 4px; padding: 5px 8px; border: 1px solid #ccc; border-radius: 3px; min-width: 150px; }
.sched-filters .sched-check { flex-direction: row; align-items: center; gap: 6px; padding-bottom: 7px; }
.sched-filters button { padding: 6px 12px; border: 1px solid #ccc; background: #fff; border-radius: 3px; }
.sched-count { font-size: 13px; color: #666; margin-bottom: 8px; }
.sched-wrap { overflow-x: auto; }
#sched-table th { cursor: pointer; white-space: nowrap; user-select: none; }
#sched-table th::after { content: " \2195"; color: #bbb; }
#sched-table th[aria-sort=ascending]::after { content: " \2191"; color: #333; }
#sched-table th[aria-sort=descending]::after { content: " \2193"; color: #333; }
#sched-table td { vertical-align: top; }
#sched-table td.nowrap { white-space: nowrap; }
#sched-table tr.bioc td { background: #eef7e6; }
#sched-table tr.bioc td:first-child { border-left: 4px solid #4fbfa8; }
.sched-tag { display: inline-block; padding: 2px 8px; border-radius: 10px; font-size: 12px; font-weight: 600; white-space: nowrap; }
.sched-tag.bioc { background: #4fbfa8; color: #fff; }
.sched-tag.abacbs { background: #e4e4e4; color: #333; }
</style>

<div class="sched-filters">
<label>Search<input type="search" id="sched-q" placeholder="Title or keyword"></label>
<label>Day<select id="sched-day"><option value="">All days</option></select></label>
<label>Session<select id="sched-session"><option value="">All sessions</option></select></label>
<label>Organiser<select id="sched-org"><option value="">All</option><option>BioC Asia</option><option>ABACBS</option></select></label>
<label class="sched-check"><input type="checkbox" id="sched-full"> ⭐ Full-session only</label>
<button type="button" id="sched-reset">Reset</button>
</div>
<div class="sched-count" id="sched-count" aria-live="polite"></div>
<div class="sched-wrap">
<table class="table" id="sched-table">
<thead><tr><th data-key="day">Day</th><th data-key="session">Session</th><th data-key="time">Time</th><th data-key="org">Organiser</th><th data-key="title">Title</th></tr></thead>
<tbody></tbody>
</table>
</div>

<script>
(function () {
  // [day, session, start, end, organiser, full-session, title]
  var rows = [
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:30 PM", "BioC Asia", false, "Keynote Speaker and Student Talks"],
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:00 PM", "ABACBS", true, "Introduction to imaging-based spatial transcriptomics analysis (Part 1)"],
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:00 PM", "ABACBS", true, "Transcripts, Embeddings, and Niches: A Practical Guide to Graph Neural Networks in Spatial Transcriptomics"],
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:00 PM", "ABACBS", true, "Multi-task single-cell omics: integration, benchmarking, and condition-aware inference"],
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:00 PM", "ABACBS", false, "From Questions to Research Strategies: Scientific Brainstorming with AI Agents"],
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:00 PM", "ABACBS", true, "Omnibenchmark: orchestrating transparent, reproducible, extensible and standardized scientific benchmarks"],
    ["Thursday, 19 November", "Afternoon 1", "1:30 PM", "3:00 PM", "ABACBS", true, "ELIXIR-GOBLET Train-the-Trainer (Part 1)"],
    ["Thursday, 19 November", "Afternoon 2", "3:30 PM", "5:00 PM", "BioC Asia", false, "blisa: Inferring Cell–Cell Communication from Spatial Transcriptomics"],
    ["Thursday, 19 November", "Afternoon 2", "3:30 PM", "5:00 PM", "ABACBS", false, "Predictive Functional Genomics: Live-Coding with AlphaGenome and Bioconductor"],
    ["Friday, 20 November", "Morning 1", "9:00 AM", "11:00 AM", "BioC Asia", false, "Keynote Speaker and Student Talks"],
    ["Friday, 20 November", "Morning 1", "9:00 AM", "10:30 AM", "ABACBS", true, "Introduction to imaging-based spatial transcriptomics analysis (Part 2)"],
    ["Friday, 20 November", "Morning 1", "9:00 AM", "10:30 AM", "ABACBS", true, "Taxonomic profiling and MAG building from long-read metagenomics"],
    ["Friday, 20 November", "Morning 1", "9:00 AM", "10:30 AM", "ABACBS", true, "From Reads to Resistance: An End-to-End Antimicrobial Resistance Analysis with BV-BRC"],
    ["Friday, 20 November", "Morning 1", "9:00 AM", "10:30 AM", "ABACBS", false, "Accelerate your Research with Cloud Computing on the ARDC Nectar Research Cloud"],
    ["Friday, 20 November", "Morning 1", "9:00 AM", "10:30 AM", "ABACBS", true, "ELIXIR-GOBLET Train-the-Trainer (Part 2)"],
    ["Friday, 20 November", "Morning 2", "11:00 AM", "12:30 PM", "BioC Asia", false, "From Reads to Isoforms: Long-Read RNA-Seq Analysis with bambu across Bulk, Single-Cell and Spatial Data"],
    ["Friday, 20 November", "Morning 2", "11:00 AM", "12:30 PM", "BioC Asia", false, "cellNexus and sccomp: From the Human Cell Atlas to insights"],
    ["Friday, 20 November", "Morning 2", "11:00 AM", "12:30 PM", "ABACBS", false, "Hello nf-core – Intermediate Nextflow training"],
    ["Friday, 20 November", "Afternoon 1", "1:00 PM", "2:30 PM", "BioC Asia", true, "Modelling continuous cell states using scRNA-seq data"],
    ["Friday, 20 November", "Afternoon 1", "1:00 PM", "2:30 PM", "BioC Asia", false, "ATAClone: Cancer Clone Identification and Copy Number Estimation from Single-cell ATAC-seq"],
    ["Friday, 20 November", "Afternoon 1", "1:00 PM", "2:30 PM", "ABACBS", false, "Spatial Taster – A quick sampler of spatial transcriptomics tests"],
    ["Friday, 20 November", "Afternoon 1", "1:00 PM", "2:30 PM", "ABACBS", false, "From Raw Reads to Cancer Insights: Hands-on Long-Read Sequencing Analysis"],
    ["Friday, 20 November", "Afternoon 1", "1:00 PM", "2:30 PM", "ABACBS", true, "Vibe-sciencing, carefully: getting real analyses out of coding agents"],
    ["Friday, 20 November", "Afternoon 1", "1:00 PM", "2:30 PM", "ABACBS", true, "Work less, garden more: Quick wins for scientific computing"],
    ["Friday, 20 November", "Afternoon 2", "3:00 PM", "4:30 PM", "BioC Asia", false, "Differential transcript expression and differential transcript usage using Salmon and edgeR"]
  ].map(function (r, i) {
    return { i: i, day: r[0], session: r[1], start: r[2], end: r[3], org: r[4], full: r[5], title: r[6] };
  });

  function mins(t) {
    var m = t.match(/(\d+):(\d+) (AM|PM)/), h = +m[1] % 12;
    return (m[3] === "PM" ? h + 12 : h) * 60 + +m[2];
  }
  var dayOrder = [], sessionOrder = [];
  rows.forEach(function (r) {
    if (dayOrder.indexOf(r.day) < 0) dayOrder.push(r.day);
    if (sessionOrder.indexOf(r.session) < 0) sessionOrder.push(r.session);
  });
  sessionOrder.sort(function (a, b) {
    var ra = rows.filter(function (r) { return r.session === a; })[0];
    var rb = rows.filter(function (r) { return r.session === b; })[0];
    return mins(ra.start) - mins(rb.start);
  });

  // Sort values per column; ties fall back to the original order (BioC Asia first per slot).
  var keyFns = {
    day: function (r) { return dayOrder.indexOf(r.day); },
    session: function (r) { return sessionOrder.indexOf(r.session); },
    time: function (r) { return dayOrder.indexOf(r.day) * 10000 + mins(r.start); },
    org: function (r) { return r.org === "BioC Asia" ? 0 : 1; },
    title: function (r) { return r.title.toLowerCase(); }
  };

  var $ = function (id) { return document.getElementById(id); };
  var table = $("sched-table"), tbody = table.querySelector("tbody");
  var sortKey = null, sortDir = 1;

  function fill(sel, values) {
    values.forEach(function (v) { var o = document.createElement("option"); o.textContent = v; sel.appendChild(o); });
  }
  fill($("sched-day"), dayOrder);
  fill($("sched-session"), sessionOrder);

  function esc(s) { var d = document.createElement("div"); d.textContent = s; return d.innerHTML; }

  function render() {
    var q = $("sched-q").value.trim().toLowerCase(), day = $("sched-day").value,
        session = $("sched-session").value, org = $("sched-org").value, full = $("sched-full").checked;
    var list = rows.filter(function (r) {
      return (!day || r.day === day) && (!session || r.session === session) &&
             (!org || r.org === org) && (!full || r.full) &&
             (!q || (r.title + " " + r.org).toLowerCase().indexOf(q) >= 0);
    });
    if (sortKey) {
      var f = keyFns[sortKey];
      list.sort(function (a, b) {
        var x = f(a), y = f(b);
        return x < y ? -sortDir : x > y ? sortDir : a.i - b.i;
      });
    }
    tbody.innerHTML = list.map(function (r) {
      var bioc = r.org === "BioC Asia";
      return '<tr class="' + (bioc ? "bioc" : "") + '">' +
        '<td class="nowrap">' + esc(r.day) + '</td>' +
        '<td class="nowrap">' + esc(r.session) + '</td>' +
        '<td class="nowrap">' + esc(r.start + "–" + r.end) + '</td>' +
        '<td><span class="sched-tag ' + (bioc ? "bioc" : "abacbs") + '">' + esc(r.org) + '</span></td>' +
        '<td>' + (r.full ? '<span title="Spans the entire morning or afternoon">⭐</span> ' : '') + esc(r.title) + '</td></tr>';
    }).join("") || '<tr><td colspan="5">No sessions match these filters.</td></tr>';
    $("sched-count").textContent = "Showing " + list.length + " of " + rows.length + " sessions";
  }

  table.querySelectorAll("th").forEach(function (th) {
    th.addEventListener("click", function () {
      var k = th.getAttribute("data-key");
      sortDir = sortKey === k ? -sortDir : 1;
      sortKey = k;
      table.querySelectorAll("th").forEach(function (h) { h.removeAttribute("aria-sort"); });
      th.setAttribute("aria-sort", sortDir === 1 ? "ascending" : "descending");
      render();
    });
  });
  ["sched-q", "sched-day", "sched-session", "sched-org", "sched-full"].forEach(function (id) {
    $(id).addEventListener("input", render);
    $(id).addEventListener("change", render);
  });
  $("sched-reset").addEventListener("click", function () {
    $("sched-q").value = ""; $("sched-day").value = ""; $("sched-session").value = "";
    $("sched-org").value = ""; $("sched-full").checked = false;
    sortKey = null;
    table.querySelectorAll("th").forEach(function (h) { h.removeAttribute("aria-sort"); });
    render();
  });
  render();
})();
</script>

<!--
+ [All short talks](../tags/short-talk/)
+ [All workshops and package demos](../workshops/)
+ Conference videos will appear on the [R Consortium](https://www.youtube.com/c/RConsortium) YouTube channel - subscribe!

{{< schedule date="Wednesday, July 27, 2022" day="day1">}}
{{< schedule date="Thursday, July 28, 2022" day="day2">}}
{{< schedule date="Friday, July 29, 2022" day="day3">}}
-->

<!--The conference will be held on the [Airmeet](https://www.airmeet.com/) virtual platform. Please, refer to the [Guide for participants](https://youtu.be/FvvZzcwlyv4) video and the [step-by-step guide how to use Airmeet](https://www.airmeet.com/hub/product-blog/step-by-step-guide-use-airmeet-for-attendees/). Please note there are no options to blur or hide your background in Airmeet; use third-party software if the blur is necessary.

Keynote sessions are 50 min, Short talk sessions (four 10-min talks) are 50 min, Package demos are 45 min, Long workshops are 90 min. Sessions during the same time slot will be run in parallel. All sessions include Q&A time.

We will be accepting abstracts for lightning talks during the conference. Watch for announcements on the first day on how to submit. If you would like to organize a meeting around a topic, challenge, geographical area, etc. during BioC2021, please, use [this form](https://forms.gle/s73DfbXPoVRe4FKj6)


- [All short talk abstracts](../short-talks)
- [All poster abstracts](../posters)
- [All workshops](../workshops), [workshop status](../workshops-status)

All times are in US Pacific Daylight savings Time (PDT). +3 hours = US EDT, +9 hours = Central European Summer Time, +15 hours = China Standard Time, +17 hours = Australian Eastern Standard Time. Time is presented in 24h format.

## Wednesday, August 4, 2021

| Time                       | Session                                     | Title &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | YouTube                               |
|----------------------------|---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| 5:00                       | Introduction                                | Intro to workshops, Icebreaker, Social/informal welcome                                                                                                                                                                                                                       | [video](https://youtu.be/6skphXuBbd4) |
| 6:00                       | Package   demo                              | [Octavio Morante-Palacios, et al., shinyEPICo: a graphical pipeline to   analyze Illumina DNA methylation arrays](../posts/paper10)                                                                                                                                           | [video](https://youtu.be/pYoId4RAsMY) |
| 6:00                       | Package   demo                              | [Federico Marini, et al., GeneTonic: enjoying the interpretation of your   RNA-seq data analysis](../posts/paper55)                                                                                                                                                           | [video](https://youtu.be/lxpm3i4PNEE) |
| 7:00                       | Long   workshop                             | [Aedin Culhane, Dimension Reduction for Beginners](../posts/paper27)                                                                                                                                                                                                          | [video](https://youtu.be/dTNMmBpizGA) |
| 7:00                       | Long   workshop                             | [Christophe Vanderaa, et al., Reproducing a single-cell proteomics data   analysis using QFeatures and scp](../posts/paper78)                                                                                                                                                 | [video](https://youtu.be/20TxPLbyE3w) |
| 7:00                       | Long   workshop                             | [Chloe Anya Mirzayi, et al., Epidemiology for   Bioinformaticians](../posts/paper121)                                                                                                                                                                                         | [video](https://youtu.be/k9XdqF0WbbQ) |
| 9:00                       | Official   welcome                          | Opening remarks                                                                                                                                                                                                                                                               | [video](https://youtu.be/vpBUahIF4xw) |
| 9:30                       | Keynote                                     | Daniela Witten, Selective inference on trees                                                                                                                                                                                                                                  | [video](https://youtu.be/rjFW4qaRPgs) |
| 10:30                      | Short   talks                               | [Methodology and statistics](../methodology-and-statistics) track                                                                                                                                                                                                             | [video](https://youtu.be/JpeXnugheAc) |
| 10:30                      | Short   talks                               | [Epigenomics/Gene regulation](../epigenomics-gene-regulation) track                                                                                                                                                                                                           | [video](https://youtu.be/zdHpSECaC6c) |
| 11:30                      | Break                                       | Networking                                                                                                                                                                                                                                                                    |                                       |
| 13:00                      | Keynote                                     | Lucia Peixoto, Reproducible Neuroscience from “omics” data analysis: a   tale of sleep and learning                                                                                                                                                                           | [video](https://youtu.be/howE6aPmOWE) |
| 14:00                      | Package   demo                              | [Dario Righelli, et al., SpatialExperiment: infrastructure for spatially   resolved transcriptomics data in R using Bioconductor](../posts/paper65)                                                                                                                           | [video](https://youtu.be/heO-TmRO1LE) |
| 14:00                      | Package   demo                              | [Aaron Chevalier, et al., Enhanced Deconvolution and Prediction of   Mutational Signatures](../posts/paper69)                                                                                                                                                                 | [video](https://youtu.be/tmVhpeYnQ4o) |
| 14:00                      | Package   demo                              | [Kai Hu, Integrated ATAC-seq Analysis with ATACseqQC / Integrated   ChIP-seq Analysis with ChIPpeakAnno](../posts/paper94)                                                                                                                                                    | [video](https://youtu.be/oYcHEXqZa1Q) |
| 15:00                      | Short   talks                               | [Transcriptomics](../transcriptomics) track                                                                                                                                                                                                                                   | [video](https://youtu.be/3xNvgPWpnxs) |
| 15:00                      | Short   talks                               | [Single-cell genomics](../single-cell-genomics) track                                                                                                                                                                                                                         | [video](https://youtu.be/4Pw7u-cJAYA) |
| 16:00                      | Break                                       | Networking                                                                                                                                                                                                                                                                    |                                       |
| 17:00                      | Package   demo                              | [Mahmoud Ahmed, et al., Chromatin segmentation analysis in   R](../posts/paper90)                                                                                                                                                                                             | [video](https://youtu.be/YvhgF-qLP_I) |
| 17:00                      | Package   demo                              | [Vincent James Carey, Integrative genetic epidemiology with OpenGWAS,   OpenCRAVAT, and Bioconductor](../posts/paper113)                                                                                                                                                      | [video](https://youtu.be/_C5dTh4ARm0) |
| 17:00                      | Package   demo                              | [Aaron R Wolen, et al., Infinitely Scalable Data Analysis in R with   TileDB](../posts/paper49)                                                                                                                                                                               | [video](https://youtu.be/CcL-xEIcHE8) |
| 18:00                      | Package   demo                              | [Pratheepa Jeganathan, et al., Statistical methods for microbiome data   analysis](../posts/paper85)                                                                                                                                                                          | [video](https://youtu.be/SdM37jaXVh4) |
| 18:00                      | Package   demo                              | [Nitesh Turaga, Fast-package installation with Bioconductor package   binaries](../posts/paper76)                                                                                                                                                                             | [video](https://youtu.be/Fd4gxJWwEbM) |
| 19:00                      | Package   demo                              | [Sean K Maden, et al., Accessing, querying, and analyzing public DNAm   array data compilations with recountmethylation](../posts/paper106)                                                                                                                                   | [video](https://youtu.be/nTysBp4fvaw) |
| 19:00                      | Package   demo                              | [David Allen Henderson, et al., Bioconductor Infrastructure Packages for   NanoString Assay Data](../posts/paper73)                                                                                                                                                           | [video](https://youtu.be/yNqoS9Y2Sy4) |
| 19:00                      | Package   demo                              | [Edward Zhao, et al., BayesSpace enables the robust characterization of   spatial gene expression architecture in tissue sections at increased   resolution](../posts/paper6)                                                                                                 | [video](https://youtu.be/vQRT8myi-qs) |

## Thursday, August 5, 2021

| Time                       | Session                                     | Title &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | YouTube                               |
|----------------------------|---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| 6:00                       | Package   demo                              | [Denes Turei, et al., OmnipathR: one   package to access more than 100 signaling databases](../posts/paper115)                                                                                                                                                                |                                       |
| 6:00                       | Package   demo                              | [Johannes Rainer, et al., Seamless Integration of Mass Spectrometry Data   from Different Sources with the Spectra Package](../posts/paper14)                                                                                                                                 | [video](https://youtu.be/CNvqlK3Wgx4) |
| 6:00                       | Package   demo                              | [Eleni Adam, et al., hummingbird: A package for detecting differential   methylation](../posts/paper59)                                                                                                                                                                       | [video](https://youtu.be/0GkNxjLUx7U) |
| 7:00                       | Long   workshop                             | [Sehyun Oh, et al., Introduction to the Terra/AnVIL Cloud-based Genomics   Platform](../posts/paper124)                                                                                                                                                                       | [video](https://youtu.be/N83iDYE2yQM) |
| 7:00                       | Long   workshop                             | [Jenny Drnevich, et al., Building Carpentries-based Bioconductor   Lessons](../posts/paper112)                                                                                                                                                                                | [video](https://youtu.be/m4ICc1yQTyY) |
| 7:00                       | Long   workshop                             | [Marcel Ramos, et al., Multi-omic Integration of cBioPortal and TCGA data   with MultiAssayExperiment](../posts/paper40)                                                                                                                                                      | [video](https://youtu.be/BY2BwYCHpUc) |
| 8:45                       | Meet   the TAB                              | Meet the TAB                                                                                                                                                                                                                                                                  | [video](https://youtu.be/cmvPHuWhacg) |
| 9:30                       | Keynote                                     | Matthew Stephens, An invitation to a multiple testing party!                                                                                                                                                                                                                  | [video](https://youtu.be/zORLq07Y5vA) |
| 10:30                      | Short   talks                               | [Transcriptomics](../transcriptomics-) track                                                                                                                                                                                                                                  | [video](https://youtu.be/eqPD6IhbMhc) |
| 10:30                      | Short   talks                               | [Apps and frameworks](../apps-and-frameworks) track                                                                                                                                                                                                                           | [video](https://youtu.be/3Vl0QtB5k-c) |
| 11:30                      | Break                                       | Networking                                                                                                                                                                                                                                                                    |                                       |
| 12:30                      | Awards                                      | Bioconductor award ceremony                                                                                                                                                                                                                                                   | [video](https://youtu.be/hOvBuJ-k1nM) |
| 13:00                      | Keynote                                     | Gabriela de Queiroz, Building a Diverse Community: The R-Ladies Story                                                                                                                                                                                                         | [video](https://youtu.be/iufMSW_gXvM) |
| 14:00                      | Birds-of-a-feather                          | [Nathan C. Sheffield, AnnotationHub   2.0: A new Bioconductor ecosystem for region data](../posts/paper100)                                                                                                                                                                   |                                       |
| 14:00                      | Career panel                                |                                                                                                                                                                                                                                                                               | [video](https://youtu.be/XeyzuLMaKQM) |
| 15:00                      | Poster   session                            | [Moderna Poster session](../posters)                                                                                                                                                                                                                                          |                                       |
| 16:00                      | Break                                       | Networking                                                                                                                                                                                                                                                                    |                                       |
| 17:00                      | Short   talks                               | [Epigenomics/Gene regulation](../epigenomics-gene-regulation-) track                                                                                                                                                                                                          | [video](https://youtu.be/oZ6kDZbFo18) |
| 17:00                      | Short   talks                               | [Education and frameworks](../education-and-frameworks) track                                                                                                                                                                                                                 | [video](https://youtu.be/p6DVdZNcUmo) |
| 18:00                      | Long   workshop                             | [Peter Hickey, Effectively using the DelayedArray framework to support   the analysis of large datasets](../posts/paper50)                                                                                                                                                    | [video](https://youtu.be/FZ8hZ4gZqTw) |
| 18:00                      | Long   workshop                             | [James MacDonald, Introduction to Bioconductor annotation   resources](../posts/paper68)                                                                                                                                                                                      | [video](https://youtu.be/3ABBm7BZszI) |
| 18:00                      | Long   workshop                             | [Hector Roux de Bezieux, et al., Trajectory inference across conditions:   differential expression and differential progression](../posts/paper80)                                                                                                                            | [video](https://youtu.be/SwDQFjmbZtg) |

## Friday, August 6, 2021

| Time                       | Session                                     | Title &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | YouTube                               |
|----------------------------|---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| 6:00                       | Poster   session                            | [Nanostring Poster   session](../posters)                                                                                                                                                                                                                                     |                                       |
| 7:00                       | Short   talks                               | [Single-cell genomics](../single-cell-genomics-) track                                                                                                                                                                                                                        | [video](https://youtu.be/X6rCbXZEoPU) |
| 7:00                       | Short   talks                               | [Proteomics/metabolomics](../proteomics-metabolomics) track                                                                                                                                                                                                                   | [video](https://youtu.be/mnfHJMKwRzc) |
| 7:00                       | Short   talks                               | [Integrative analysis](../integrative-analysis) track                                                                                                                                                                                                                         | [video](https://youtu.be/OQ-0Aa5J4ec) |
| 8:00                       | Package   demo                              | [Nils Eling, Visualisation of highly-multiplexed imaging data in   R](../posts/paper1)                                                                                                                                                                                        | [video](https://youtu.be/DYYuAPcBf8s) |
| 8:00                       | Package   demo                              | [Pacome Prompsy, Interactive analysis of single-cell epigenomic   landscapes with ChromSCape](../posts/paper2)                                                                                                                                                                | [video](https://youtu.be/Illy08-W56k) |
| 8:00                       | Package   demo                              | [Federico Agostinis, et al., NewWave, new R package for dimensional   reduction and batch effect removal for single cell RNA-seq   data](../posts/paper11)                                                                                                                    | [video](https://youtu.be/_WYS-JFdVrU) |
| 8:45                       | Meet the core team                          |                                                                                                                                                                                                                                                                               | [video](https://youtu.be/O2WOTclMk18) |
| 9:30                       | Keynote                                     | Amanda Haddock, Redefining the Patient's Role in the Genomics Era                                                                                                                                                                                                             | [video](https://youtu.be/OqZ44OqESlM) |
| 10:30                      | Short   talks                               | [Infrastructure/programming](../infrastructure-programming) track                                                                                                                                                                                                             | [video](https://youtu.be/BXX-Q7HosnM) |
| 10:30                      | Short   talks                               | [Microbiome/metagenomics](../microbiome-metagenomics) track                                                                                                                                                                                                                   | [video](https://youtu.be/Gv1ud-JG0ms) |
| 11:30                      | Break                                       | Networking                                                                                                                                                                                                                                                                    |                                       |
| 13:00                      | Keynote                                     | Melissa Wilson, Sex-biased genomics and methodology                                                                                                                                                                                                                           | [video](https://youtu.be/WPy3_IWa5gA) |
| 14:00                      | Meet the CAB                                |                                                                                                                                                                                                                                                                               | [video](https://youtu.be/LTT1i_ACpxc) |
| 15:00                      | Lightning talks                             |                                                                                                                                                                                                                                                                               | [video](https://youtu.be/nGQ6Y3GmYL4) |
| 16:00                      | Break                                       | Networking                                                                                                                                                                                                                                                                    |                                       |
| 17:00                      | Package   demo                              | [Lukas M Weber, et al., Orchestrating Spatially Resolved Transcriptomics   Analysis with Bioconductor (OSTA)](../posts/paper74)                                                                                                                                               | [video](https://youtu.be/dXF7Rv2UwdI) |
| 17:00                      | Package   demo                              | [Nitesh Turaga, K8sredis: On-demand parallel computing Kubernetes   application for Bioconductor users](../posts/paper82)                                                                                                                                                     | [video](https://youtu.be/D8eNwVfLJKo) |
| 18:00                      | Long   workshop                             | [Daniela Cassol, et al., systemPipe: Workflow and Visualization   Toolkit](../posts/paper81)                                                                                                                                                                                  | [video](https://youtu.be/_C4K7TFicDo) |
| 18:00                      | Long   workshop                             | [Stefano Mangiola, et al., Interfacing Bioconductor with tidyverse with   tidySingleCellExperiment and tidySummarisedExperiment](../posts/paper9)                                                                                                                             | [video](https://youtu.be/kmfIFIgVwvc) |
| 19:45                      | Closing   remarks                           | Networking                                                                                                                                                                                                                                                                    | [video](https://youtu.be/N7LCSUWYof0) |


Change the time zone in the teamup calendar ('hamburger button' in the upper-right corner). Add this calendar to your calendar using "Preferences/iCalendar Feeds". 

{{< iframe >}}
-->
