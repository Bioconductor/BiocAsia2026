+++
title = "Schedule"
description = "Schedule"
+++

BioC Asia 2026 is held alongside the ABACBS 2026 workshops at **Building 80, RMIT University City Campus, Melbourne** on Thursday 19 and Friday 20 November 2026.

<a class="cta-button" href="https://www.abacbs.org/workshops-2026-call" target="_blank" rel="noopener">Register Now</a>

See the [Registration](/registration/) page for prices and options.

## BioC Asia highlights

<div class="sched-highlights">
<div class="sched-hl"><div class="sched-hl-when">Thu 19 Nov · 1:15–2:00 PM · 080.06.05</div><div class="sched-hl-what"><strong>Keynote:</strong> Dr. Charity Law (WEHI)</div></div>
<div class="sched-hl"><div class="sched-hl-when">Thu 19 Nov · 4:00–5:30 PM · 080.06.05</div><div class="sched-hl-what">Global BioC Asia community talk, student talks and community discussion</div></div>
<div class="sched-hl"><div class="sched-hl-when">Thu 19 Nov · 6:00 PM–late</div><div class="sched-hl-what"><strong>Community meetup</strong> at the Oxford Scholar (outside Building 80), sponsored by Bioconductor</div></div>
<div class="sched-hl"><div class="sched-hl-when">Fri 20 Nov · 9:00–9:45 AM · 080.06.05</div><div class="sched-hl-what"><strong>Keynote:</strong> Prof. Mark Robinson (University of Zurich)</div></div>
<div class="sched-hl"><div class="sched-hl-when">Fri 20 Nov · 9:45–10:30 AM · 080.06.05</div><div class="sched-hl-what">Global BioC Asia community talk and student talks</div></div>
<div class="sched-hl"><div class="sched-hl-when">Thu &amp; Fri</div><div class="sched-hl-what">Five hands-on BioC Asia workshops: blisa, bambu, cellNexus &amp; sccomp, continuous cell states, and Salmon &amp; edgeR</div></div>
</div>

## Full program

BioC Asia sessions are shown first and highlighted in green. ABACBS workshops running at the same time are listed too. Click a column heading to sort, or use the filters to narrow the list.

Venue codes (e.g. 080.06.05) read as Building 80, Floor 06, Room 05. Workshops are subject to availability.

<style>
.sched-highlights { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 12px; margin: 12px 0 28px; }
.sched-hl { border-left: 4px solid #4fbfa8; background: #eef7e6; padding: 10px 14px; border-radius: 3px; }
.sched-hl-when { font-size: 12px; font-weight: 600; color: #2f6b57; margin-bottom: 4px; }
.sched-hl-what { font-size: 14px; }
.sched-filters { display: flex; flex-wrap: wrap; gap: 10px 16px; align-items: flex-end; margin: 20px 0 12px; }
.sched-filters label { display: flex; flex-direction: column; font-weight: 600; font-size: 13px; margin: 0; }
.sched-filters select, .sched-filters input[type=search] { font-weight: normal; margin-top: 4px; padding: 5px 8px; border: 1px solid #ccc; border-radius: 3px; min-width: 150px; }
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
#sched-table tr.abacbs td { color: #555; }
#sched-table .sched-speaker { display: block; font-size: 13px; color: #555; margin-top: 2px; }
.sched-tag { display: inline-block; padding: 2px 8px; border-radius: 10px; font-size: 12px; font-weight: 600; white-space: nowrap; }
.sched-tag.bioc { background: #4fbfa8; color: #fff; }
.sched-tag.abacbs { background: #f5d77a; color: #333; }
</style>

<div class="sched-filters">
<label>Search<input type="search" id="sched-q" placeholder="Title, speaker or room"></label>
<label>Day<select id="sched-day"><option value="">All days</option></select></label>
<label>Organiser<select id="sched-org"><option value="">All</option><option>BioC Asia</option><option>ABACBS</option></select></label>
<label>Type<select id="sched-type"><option value="">All types</option></select></label>
<button type="button" id="sched-reset">Reset</button>
</div>
<div class="sched-count" id="sched-count" aria-live="polite"></div>
<div class="sched-wrap">
<table class="table" id="sched-table">
<thead><tr><th data-key="day">Day</th><th data-key="time">Time</th><th data-key="room">Room</th><th data-key="org">Organiser</th><th data-key="type">Type</th><th data-key="title">Session</th></tr></thead>
<tbody></tbody>
</table>
</div>

<script>
(function () {
  // [day, start, end, room, organiser, type, title, speaker]
  var rows = [
    ["Thursday, 19 November", "1:15 PM", "2:00 PM", "080.06.05", "BioC Asia", "Keynote", "Keynote", "Dr. Charity Law (WEHI)"],
    ["Thursday, 19 November", "2:00 PM", "3:30 PM", "080.07.06", "BioC Asia", "Workshop", "blisa: Inferring Cell–Cell Communication from Spatial Transcriptomics", ""],
    ["Thursday, 19 November", "2:00 PM", "5:30 PM", "080.07.02", "ABACBS", "Workshop", "Transcripts, Embeddings, and Niches: A Practical Guide to Graph Neural Networks in Spatial Transcriptomics", ""],
    ["Thursday, 19 November", "2:00 PM", "5:30 PM", "080.08.09", "ABACBS", "Workshop", "Multi-task Single-cell Omics: Integration, Benchmarking, and Condition-aware Inference", ""],
    ["Thursday, 19 November", "2:00 PM", "5:30 PM", "080.07.09", "ABACBS", "Workshop", "Swarm in The Lab: Building a Fleet of Biomedical AI Agents with Virtual Lab, Paper2Agent and the Virtual Biotech platforms", ""],
    ["Thursday, 19 November", "4:00 PM", "4:15 PM", "080.06.05", "BioC Asia", "Community talk", "Global BioC Asia Community Talk", "Jyoti Bhogal"],
    ["Thursday, 19 November", "4:15 PM", "4:25 PM", "080.06.05", "BioC Asia", "Student talk", "blisa: Inferring Cell–Cell Communication in Spatial Transcriptomics", "Lei Qin"],
    ["Thursday, 19 November", "4:25 PM", "4:35 PM", "080.06.05", "BioC Asia", "Student talk", "Accelerating Antiviral Guide RNA Design with Machine Learning-Informed CRISPR-Cas13b Targeting", "Phan Dang Khoa"],
    ["Thursday, 19 November", "4:35 PM", "4:45 PM", "080.06.05", "BioC Asia", "Student talk", "Systematic benchmarking of spatial transcriptomics analysis workflows using SpaBench", "Yang Xu"],
    ["Thursday, 19 November", "4:45 PM", "5:30 PM", "080.06.05", "BioC Asia", "Community", "Community discussion", ""],
    ["Thursday, 19 November", "6:00 PM", "late", "Oxford Scholar", "BioC Asia", "Social", "Community meetup (Oxford Scholar, outside Building 80), sponsored by Bioconductor", ""],
    ["Friday, 20 November", "9:00 AM", "9:45 AM", "080.06.05", "BioC Asia", "Keynote", "Keynote", "Prof. Mark Robinson (University of Zurich)"],
    ["Friday, 20 November", "9:45 AM", "10:00 AM", "080.06.05", "BioC Asia", "Community talk", "Global BioC Asia Community Talk", "Zuguang Gu"],
    ["Friday, 20 November", "10:00 AM", "10:10 AM", "080.06.05", "BioC Asia", "Student talk", "SPAROscore: sparsity-adaptive gene-set scoring", "Venkatesh Kamaraj"],
    ["Friday, 20 November", "10:10 AM", "10:20 AM", "080.06.05", "BioC Asia", "Student talk", "Optimising Gene Therapy Delivery: Targeting Specific Cell Types and Tissues with Recombinant Adeno-Associated Virus for Precision Medicine", "Natsuki Sasaki"],
    ["Friday, 20 November", "10:20 AM", "10:30 AM", "080.06.05", "BioC Asia", "Student talk", "Computational Discovery of Immunodominant and Evolutionarily Robust T-Cell Targets for Rational Dengue Vaccine Design", "Jingjing Liu"],
    ["Friday, 20 November", "11:00 AM", "12:30 PM", "080.07.09", "BioC Asia", "Workshop", "From Reads to Isoforms: Long-Read RNA-Seq Analysis with bambu across Bulk, Single-Cell and Spatial Data", ""],
    ["Friday, 20 November", "11:00 AM", "12:30 PM", "080.08.09", "BioC Asia", "Workshop", "cellNexus and sccomp: From the Human Cell Atlas to insights", ""],
    ["Friday, 20 November", "11:00 AM", "2:30 PM", "080.07.08", "ABACBS", "Workshop", "Taxonomic profiling and MAG building from long-read metagenomics", ""],
    ["Friday, 20 November", "11:00 AM", "12:30 PM", "080.07.02", "ABACBS", "Workshop", "Accelerate your Research with Cloud Computing on the ARDC Nectar Research Cloud", ""],
    ["Friday, 20 November", "1:00 PM", "4:30 PM", "080.07.02", "BioC Asia", "Workshop", "Modelling continuous cell states using scRNA-seq data", ""],
    ["Friday, 20 November", "1:00 PM", "2:30 PM", "080.08.09", "ABACBS", "Workshop", "From Raw Reads to Cancer Insights: Hands-on Long-Read Sequencing Analysis", ""],
    ["Friday, 20 November", "1:00 PM", "4:30 PM", "080.07.09", "ABACBS", "Workshop", "Vibe-sciencing, carefully: getting real analyses out of coding agents", ""],
    ["Friday, 20 November", "3:00 PM", "4:30 PM", "080.07.06", "BioC Asia", "Workshop", "Differential transcript expression and differential transcript usage using Salmon and edgeR", ""]
  ].map(function (r, i) {
    return { i: i, day: r[0], start: r[1], end: r[2], room: r[3], org: r[4], type: r[5], title: r[6], speaker: r[7] };
  });

  function mins(t) {
    var m = t.match(/(\d+):(\d+) (AM|PM)/), h = +m[1] % 12;
    return (m[3] === "PM" ? h + 12 : h) * 60 + +m[2];
  }
  function uniq(key) {
    var out = [];
    rows.forEach(function (r) { if (out.indexOf(r[key]) < 0) out.push(r[key]); });
    return out;
  }
  var dayOrder = uniq("day");

  // Sort values per column; ties fall back to day, then start time with BioC Asia first.
  var keyFns = {
    day: function (r) { return dayOrder.indexOf(r.day); },
    time: function (r) { return dayOrder.indexOf(r.day) * 10000 + mins(r.start); },
    room: function (r) { return r.room; },
    org: function (r) { return r.org === "BioC Asia" ? 0 : 1; },
    type: function (r) { return r.type; },
    title: function (r) { return r.title.toLowerCase(); }
  };
  function defaultOrder(a, b) {
    return keyFns.time(a) - keyFns.time(b) || keyFns.org(a) - keyFns.org(b) || a.i - b.i;
  }

  var $ = function (id) { return document.getElementById(id); };
  var table = $("sched-table"), tbody = table.querySelector("tbody");
  var sortKey = null, sortDir = 1;

  function fill(sel, values) {
    values.forEach(function (v) { var o = document.createElement("option"); o.textContent = v; sel.appendChild(o); });
  }
  fill($("sched-day"), dayOrder);
  fill($("sched-type"), uniq("type").sort());

  function esc(s) { var d = document.createElement("div"); d.textContent = s; return d.innerHTML; }

  function render() {
    var q = $("sched-q").value.trim().toLowerCase(), day = $("sched-day").value,
        org = $("sched-org").value, type = $("sched-type").value;
    var list = rows.filter(function (r) {
      return (!day || r.day === day) && (!org || r.org === org) && (!type || r.type === type) &&
             (!q || [r.title, r.speaker, r.room, r.org, r.type].join(" ").toLowerCase().indexOf(q) >= 0);
    });
    list.sort(function (a, b) {
      if (sortKey) {
        var x = keyFns[sortKey](a), y = keyFns[sortKey](b);
        if (x < y) return -sortDir;
        if (x > y) return sortDir;
      }
      return defaultOrder(a, b);
    });
    tbody.innerHTML = list.map(function (r) {
      var bioc = r.org === "BioC Asia";
      return '<tr class="' + (bioc ? "bioc" : "abacbs") + '">' +
        '<td class="nowrap">' + esc(r.day) + '</td>' +
        '<td class="nowrap">' + esc(r.start + "–" + r.end) + '</td>' +
        '<td class="nowrap">' + esc(r.room) + '</td>' +
        '<td><span class="sched-tag ' + (bioc ? "bioc" : "abacbs") + '">' + esc(r.org) + '</span></td>' +
        '<td class="nowrap">' + esc(r.type) + '</td>' +
        '<td>' + esc(r.title) + (r.speaker ? '<span class="sched-speaker">' + esc(r.speaker) + '</span>' : '') + '</td></tr>';
    }).join("") || '<tr><td colspan="6">No sessions match these filters.</td></tr>';
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
  ["sched-q", "sched-day", "sched-org", "sched-type"].forEach(function (id) {
    $(id).addEventListener("input", render);
    $(id).addEventListener("change", render);
  });
  $("sched-reset").addEventListener("click", function () {
    $("sched-q").value = ""; $("sched-day").value = ""; $("sched-org").value = ""; $("sched-type").value = "";
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
