---
UID: NN:sensorsclassextension.ISensorClassExtension
title: ISensorClassExtension
author: windows-driver-content
description: The ISensorClassExtension interface provides methods that the sensor driver uses to communicate with the sensor platform (and, therefore, client applications) through the sensor class extension object.
old-location: sensors\isensorclassextension.htm
old-project: sensors
ms.assetid: db455be3-3aec-47c4-81a8-992aa4926138
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sensors.isensorclassextension, ISensorClassExtension interface [Sensor Devices], ISensorClassExtension interface [Sensor Devices], described, ISensorClassExtension, sensorsclassextension/ISensorClassExtension, Sensor_IFaces_84ca9d2b-f0e3-4500-99a4-21054c7dc527.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
apiname:
-	ISensorClassExtension
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorClassExtension interface


## -description


The ISensorClassExtension interface provides methods that the sensor driver uses to communicate with the sensor platform (and, therefore, client applications) through the sensor class extension object.


## -members

The <b>ISensorClassExtension</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545512">ISensorClassExtension::CleanupFile</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545514">ISensorClassExtension::Initialize</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545519">ISensorClassExtension::PostEvent</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ae3bc846-df63-4186-9554-f4600e1f2066">ISensorClassExtension::PostStateChange</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545536">ISensorClassExtension::ProcessIoControl</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545547">ISensorClassExtension::Uninitialize</a>
</td>
<td align="left" width="63%"></td>
</tr>
</table> 

