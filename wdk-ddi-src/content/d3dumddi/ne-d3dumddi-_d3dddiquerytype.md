---
UID: NE:d3dumddi._D3DDDIQUERYTYPE
title: _D3DDDIQUERYTYPE (d3dumddi.h)
description: The query type.
ms.date: 10/19/2018
keywords: ["D3DDDIQUERYTYPE enumeration"]
ms.keywords: _D3DDDIQUERYTYPE, D3DDDIQUERYTYPE,
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DDDIQUERYTYPE
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DDDIQUERYTYPE
 - d3dumddi/_D3DDDIQUERYTYPE
 - D3DDDIQUERYTYPE
 - d3dumddi/D3DDDIQUERYTYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIQUERYTYPE
 - D3DDDIQUERYTYPE
product:
 - Windows
dev_langs:
 - c++
---

# _D3DDDIQUERYTYPE enumeration


## -description

The query type.

## -enum-fields

### -field D3DDDIQUERYTYPE_VCACHE

Query at issue end for driver hints about data layout for vertex caching. This query is processed through a call to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_issuequery">IssueQuery</a> function in which the <b>End</b> bit-field flag is set in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_issuequery">D3DDDIARG_ISSUEQUERY</a> structure.

### -field D3DDDIQUERYTYPE_RESOURCEMANAGER

Query the driver's resource manager.

### -field D3DDDIQUERYTYPE_VERTEXSTATS

Query for the vertex stats.

### -field D3DDDIQUERYTYPE_DDISTATS

Query for the DDI stats.

### -field D3DDDIQUERYTYPE_EVENT

Query at issue end for asynchronous events that have occurred.

### -field D3DDDIQUERYTYPE_OCCLUSION

Query for the number of pixels that pass z-testing. These pixels are for primitives that are drawn between an issue begin and an issue end.

This query is processed between calls to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_issuequery">IssueQuery</a> function in which first the <b>Begin</b> bit-field flag is set in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_issuequery">D3DDDIARG_ISSUEQUERY</a> structure and next the <b>End</b> bit-field flag is set.

This query enables an application to check the occlusion result against 0. A value of 0 is "fully occluded," which means the pixels are not visible from the current camera position.

### -field D3DDDIQUERYTYPE_TIMESTAMP

Query at issue end for the 64-bit timestamp.

### -field D3DDDIQUERYTYPE_TIMESTAMPDISJOINT

This query is used to notify an application whether the counter frequency has changed from the value that is returned from the D3DQUERYTYPE_TIMESTAMP query.

### -field D3DDDIQUERYTYPE_TIMESTAMPFREQ

The GPU timestamp frequency for resolving query timestamps.

This query result is <b>TRUE</b> if the values from D3DQUERYTYPE_TIMESTAMP queries cannot be guaranteed to be continuous throughout the duration of the D3DQUERYTYPE_TIMESTAMPDISJOINT query. Otherwise, the query result is <b>FALSE</b>.

### -field D3DDDIQUERYTYPE_PIPELINETIMINGS

Query for the percent of processing time spent on pipeline data.

### -field D3DDDIQUERYTYPE_INTERFACETIMINGS

Query for the percent of processing time spent on data in the driver.

### -field D3DDDIQUERYTYPE_VERTEXTIMINGS

Query for the percent of processing time spent on vertex shader data.

### -field D3DDDIQUERYTYPE_PIXELTIMINGS

Query for the percent of processing time spent on pixel shader data.

### -field D3DDDIQUERYTYPE_BANDWIDTHTIMINGS

Query for throughput measurements for help in understanding the performance of an application.

### -field D3DDDIQUERYTYPE_CACHEUTILIZATION

Query for the cache hit-rate performance for textures and indexed vertices.

### -field D3DDDIQUERYTYPE_COUNTER_DEVICE_DEPENDENT

Query for device-dependent counters.

## -remarks

## -see-also

