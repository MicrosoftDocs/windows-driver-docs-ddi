---
UID: NN:sensorsclassextension.ISensorDriver
title: ISensorDriver
author: windows-driver-content
description: The ISensorDriver interface provides callback methods that the sensor class extension uses to provide requests and notifications to the sensor driver.
old-location: sensors\isensordriver.htm
old-project: sensors
ms.assetid: 4f468f1e-598e-46ae-b50e-28f73e73afda
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.isensordriver, ISensorDriver interface [Sensor Devices], ISensorDriver interface [Sensor Devices], described, ISensorDriver, sensorsclassextension/ISensorDriver, Sensor_IFaces_014342f2-5466-426b-bb11-cb4e89a7691a.xml
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
-	ISensorDriver
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorDriver interface


## -description



The ISensorDriver interface provides callback methods that the sensor class extension uses to provide requests and notifications to the sensor driver.




## -members

The <b>ISensorDriver</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545573">ISensorDriver::OnClientConnect</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/9484610b-4cbd-4c4e-9e60-ef052702325c">ISensorDriver::OnClientDisconnect</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545589">ISensorDriver::OnClientSubscribeToEvents</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545598">ISensorDriver::OnClientUnsubscribeFromEvents</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545607">ISensorDriver::OnGetDataFields</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545620">ISensorDriver::OnGetSupportedDataFields</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545623">ISensorDriver::OnGetSupportedEvents</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545630">ISensorDriver::OnGetSupportedProperties</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545633">ISensorDriver::OnGetSupportedSensorObjects</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545644">ISensorDriver::OnProcessWpdMessage</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7c3cca5b-1d08-42dc-8dc4-42eb1160b8bb">ISensorDriver::OnSetProperties</a>
</td>
<td align="left" width="63%"></td>
</tr>
</table> 

