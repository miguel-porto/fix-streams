# fix-streams
<h1>R script to fix multiple confluences in stream networks</h1>
<p>All nodes which have >2 streams flowing to it are corrected. The outermost streams' end vertices are adjusted by "step" meters along the downgoing stream. New nodes are created at suitable places, and existing lines suitably split.</p>
<p>Requires a line shapefile with the proper FROM_NODE and TO_NODE fields. The file is assumed to be correct in all other aspects, there is no error checking.</p>
<h2>USAGE EXAMPLE</h2>
<code>
rios=readOGR("streams_Pt.shp","streams_Pt")
correctedshp=fix.streams(rios,step=10)
writeOGR(correctedshp,"streams_corrected.shp","streams_corrected","ESRI Shapefile")
</code>
