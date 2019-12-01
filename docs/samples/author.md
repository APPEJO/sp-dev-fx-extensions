# Samples by Author

Our samples were created by the feature teams, SharePoint PnP core team (http://aka.ms/SharePointPnP) or shared by the community. Use the filter below to find samples by author.

<div class="well">

<input list="authors" name="author" class="form-control" placeholder="Type to search by author" id="author" />
<datalist id="authors">
  {% for author in authors %}
    <option value="{{ author }}">
  {% endfor %}
</datalist>

<br/>

<div class="grid">

{% for sample in samples|sort(attribute='modified', reverse=True) %}

<div class="sample-item" data-author="{{ sample.author }}">
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