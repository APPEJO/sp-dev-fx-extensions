# Samples by Keyword

Use the filter below to find samples by keywords in the title or description.

<div class="well">

<input name="keyword" class="form-control" placeholder="Type to search by keyword" id="keyword" />

<br/>

<div class="grid">

{% for sample in samples|sort(attribute='modified', reverse=True) %}

<div class="sample-item" data-keywords="{{ sample.name }} {{ sample.title }} {{ sample.summary }}">
  <div class="sample">
  {% if sample.thumbnailtype == "video" %}
    <div class="sample-video"><i class="ms-Icon ms-Icon--VideoSolid" aria-hidden="true"></i></div>
    {% endif %}
    <div class="sample-img">
      <a class="sample-link"
        href="{{sample.url}}"
        title="{{sample.title}}">
        <picture>
          <img src="../../img/thumbnails/sm/{{ sample.name }}.png" width="302" alt="{{sample.name}}" data-fullsize="{{sample.thumbnail}}" data-orig="../../img/thumbnails/sm/{{ sample.name }}.png"/>
        </picture>
      </a>
    </div>
  </div>
      <a href="{{sample.url}}"
      title="{{ sample.title }}">
  <h2 class="name">
      {{sample.title}}</h2>
      <div class="sample-activity">
  <span class="author" title="{{ sample.author }}">{{ sample.author }}</span>
  <span class="modified">Modified {{ sample.modifiedtext }}</span>
  </div>
  </a>

</div>
    {% endfor %}
</div>

<img src="https://telemetry.sharepointpnp.com/sp-dev-fx-webparts/docs/samples/author" />