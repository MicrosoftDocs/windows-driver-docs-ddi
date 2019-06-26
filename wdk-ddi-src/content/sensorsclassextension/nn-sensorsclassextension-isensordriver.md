---
UID: NN:sensorsclassextension.ISensorDriver
title: ISensorDriver (sensorsclassextension.h)
description: The ISensorDriver interface provides callback methods that the sensor class extension uses to provide requests and notifications to the sensor driver.
old-location: sensors\isensordriver.htm
tech.root: sensors
ms.assetid: 4f468f1e-598e-46ae-b50e-28f73e73afda
ms.date: 05/03/2018
ms.keywords: ISensorDriver, ISensorDriver interface [Sensor Devices], ISensorDriver interface [Sensor Devices],described, Sensor_IFaces_014342f2-5466-426b-bb11-cb4e89a7691a.xml, sensors.isensordriver, sensorsclassextension/ISensorDriver
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- SensorsClassExtension.lib
- SensorsClassExtension.dll
api_name:
- ISensorDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorDriver interface


## -description



The ISensorDriver interface provides callback methods that the sensor class extension uses to provide requests and notifications to the sensor driver.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">ISensorDriver</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>ISensorDriver</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>ISensorDriver</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientconnect">ISensorDriver::OnClientConnect</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientdisconnect">ISensorDriver::OnClientDisconnect</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientsubscribetoevents">ISensorDriver::OnClientSubscribeToEvents</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientunsubscribefromevents">ISensorDriver::OnClientUnsubscribeFromEvents</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetdatafields">ISensorDriver::OnGetDataFields</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetproperties">ISensorDriver::OnGetProperties</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupporteddatafields">ISensorDriver::OnGetSupportedDataFields</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupportedevents">ISensorDriver::OnGetSupportedEvents</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupportedproperties">ISensorDriver::OnGetSupportedProperties</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupportedsensorobjects">ISensorDriver::OnGetSupportedSensorObjects</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-onprocesswpdmessage">ISensorDriver::OnProcessWpdMessage</a>
</td>
<td align="left" width="63%"></td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsclassextension/nf-sensorsclassextension-isensordriver-onsetproperties">ISensorDriver::OnSetProperties</a>
</td>
<td align="left" width="63%"></td>
</tr>
</table> 

