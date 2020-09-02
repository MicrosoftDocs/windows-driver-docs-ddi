---
UID: NF:ks.KsFastPropertyHandler
title: KsFastPropertyHandler function (ks.h)
description: The KsFastPropertyHandler function handles fast property requests through IOCTL_KS_PROPERTY. It responds to all property identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksfastpropertyhandler.htm
tech.root: stream
ms.assetid: 39a216f8-297d-45cc-9bec-4c0ee9941441
ms.date: 04/23/2018
keywords: ["KsFastPropertyHandler function"]
ms.keywords: KsFastPropertyHandler, KsFastPropertyHandler function [Streaming Media Devices], ks/KsFastPropertyHandler, ksfunc_4b896ea0-aa74-4acf-b8fa-cdc4c8cdb4b1.xml, stream.ksfastpropertyhandler
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFastPropertyHandler
 - ks/KsFastPropertyHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFastPropertyHandler
---

# KsFastPropertyHandler function


## -description

The <b>KsFastPropertyHandler</b> function handles fast property requests through IOCTL_KS_PROPERTY. It responds to all property identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.

## -parameters

### -param FileObject

### -param Property

### -param PropertyLength

### -param Data

### -param DataLength

### -param IoStatus

### -param PropertySetsCount

### -param PropertySet

## -returns

The <b>KsFastPropertyHandler</b> function returns <b>TRUE</b> if the request was handled, or <b>FALSE</b> if the request was not handled. If <b>FALSE</b> is returned, an IRP is generated. If the request was handled, the function sets the IoStatus->Information element, either through setting it to zero because of an internal error, or through a property handler setting it. The property handler also sets the IoStatus->Status field when the property is actually handled.

## -remarks

The owner of a property set can perform prefiltering or postfiltering of the property handling, as well as processing requests made through the fast I/O dispatch interface for device control. The <b>KsFastPropertyHandler</b> function is only used to process requests that can be fulfilled quickly.  The <i>Wait</i> parameter of the fast I/O function is not passed and is assumed to be <b>TRUE</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspropertyhandler">KsPropertyHandler</a>

