# What is a FAIR-IO
A FAIR-IO (FAIR Image Object) bundle combines acquisition and provenance metadata together with multi-resolution, chunked binary pixel data in a single cloud-compatible format for simplified sharing and re-use. As such, FAIR-IO implements
a FAIR Digital Object (FDO, DOI:10.5281/zenodo.7824714) as illustrated below.

![FAIR-IO concept](FAIR-IO_10.5281-zenodo.10512531.png)

FAIR-IO is based on the following recommendations for binary (pixel) data and textual metadata.
## Recommendations for easily sharable binary data: 
<div>
<table style="margin-left:5px;">
<tr>
    <!--<td style="text-align:left;"><img src="FAIR-IO_inner.png" style="width:120px; float:left" ></td>-->
    <td>
        <ul>
          <li>Use data formats that store binary data with multiple resolutions in a single cloud-compatible, chunkable format. These enable web-optimised data access and high-performance cloud storage</li>
          <li>Store data in a public available space accessible via a data specific URL</li> 
        </ul>
        <b>Example format:</b> ome-zarr (<a href="https://doi.org/10.1007/s00418-023-02209-1"> About</a> |<a href=""> Tools</a>)
    </td>
</tr>

</table>
</div>


## Recommendations for easily sharable metadata:
<div>
<table style="margin-left:5px;">
<tr>
    <!--<td style="text-align:left;"><img src="FAIR-IO_middle.png" style="width:80px; float:left" ></td>-->
    <td>
        <ul>
          <li>Ensure that the relationship and meaning of the data is clear described or linked</li>
          <li>Use metadata formats that store metadata in a machine readable form, that means </li>
          <li>store data in a public available space accessible via a data specific URL</li> 
        </ul>
        <b>Example formats:</b> JSON-LD (<a href=""> About</a> |<a href=""> Tools</a>), Turtle (<a href=""> About</a> |<a href=""> Tools</a>)
    </td>
</tr>
</table>
</div>







