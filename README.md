# fix-streams
<h1>R script to fix multiple confluences in river networks</h1>
<p>This script corrects all nodes in a river network which have more than 2 streams flowing to them. The outermost streams' end vertices are adjusted by <code>step</code> meters along the downgoing stream. New nodes are created at suitable places, and existing lines suitably split. This is useful for correcting river networks before using network analysis tools which don't allow complex confluences, such as <a href="http://www.fs.fed.us/rm/boise/AWAE/projects/SpatialStreamNetworks.shtml" target="_blank">STARS</a></p>
<p>Requires a line shapefile with the proper FROM_NODE and TO_NODE fields. The file is assumed to be correct in all other aspects, <em>there is no error checking</em>, so carefully check the result.</p>
<h2>Usage example</h2>
<code>streams=readOGR("streams_Pt.shp","streams_Pt")</code><br/>
<code>correctedshp=fix.streams(streams,step=10)</code><br/>
<code>writeOGR(correctedshp,"streams_corrected.shp","streams_corrected","ESRI Shapefile")</code>
