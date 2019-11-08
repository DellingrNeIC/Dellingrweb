---
layout: master
title: Available offerings
---

<table id="dtBasicExample" class="table table-striped table-bordered table-sm" cellspacing="0" width="100%">
  <thead>
    <tr>
      <th class="th-sm">Name
      </th>
      <th class="th-sm">Description
      </th>
      <th class="th-sm">Owner
      </th>
      <th class="th-sm">Node count
      </th>
      <th class="th-sm">Theoretical TFlops
      </th>
      <th class="th-sm">RAM (GB/node)
      </th>
      <th class="th-sm">GPU type
      </th>
      <th class="th-sm">Status
      </th>
    </tr>
  </thead>
  <tbody>

{% assign default_array = "" | split: "" %}

{% for offering in site.data.offerings %}
    <tr>
      <td><a href="{{ offering.attributes.support_guide }}">{{ offering.name }}</a></td>
      <td>{{ offering.description }}</td>
      <td>{{ offering.customer_name }}</td>
      <td>{{ offering.attributes.hpc_node_information_node_count }}</td>
      <td>{{ offering.attributes.hpc_performance_tflops }}</td>
      <td>{{ offering.attributes.hpc_node_information_memory }}</td>
      <td>{{ offering.attributes.hpc_node_information_gpu | default:default_array | array_to_sentence_string: "and" | remove: "node_information_gpu_" }}</td>
      <td>{{ offering.state }}</td>
    </tr>
{% endfor %}
  </tbody>
</table>

{% comment %}

<div id="mapid"></div>

<script>
var mymap = L.map('mapid').setView([51.505, -0.09], 13);

var circle = L.circle([51.508, -0.11], {
    color: 'red',
    fillColor: '#f03',
    fillOpacity: 0.5,
    radius: 500
}).addTo(mymap);

</script>
{% endcomment %}
