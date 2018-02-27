---
UID: NA:sensorsclassextension
ms.assetid: 9181ae48-c50e-3f5e-942d-1030b8e2c0b5
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sensorsclassextension.h header



This header is used by Sensors. For more information, see
- [Sensors](../_sensors/index.md)

Sensorsclassextension.h contain these programming interfaces:


## Enumerations

| Title   | Description   |
| ---- |:---- |
| [LOCATION_DESIRED_ACCURACY enumeration](ne-sensorsclassextension-location_desired_accuracy.md) | The LOCATION_DESIRED_ACCURACY enumeration type defines values for the SENSOR_PROPERTY_LOCATION_DESIRED_ACCURACY property. |
| [MagnetometerAccuracy enumeration](ne-sensorsclassextension-magnetometeraccuracy.md) | Specifies the accuracy of the magnetometer. |
| [__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001 enumeration](ne-sensorsclassextension-__midl___midl_itf_windowssensorclassextension_0000_0000_0001.md) | The SensorState enumeration type specifies the current operational state of a sensor. |
| [__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0002 enumeration](ne-sensorsclassextension-__midl___midl_itf_windowssensorclassextension_0000_0000_0002.md) | The SensorConnectionType enumeration type defines values for the SENSOR_CONNECTION_TYPE property. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [ISensorClassExtension interface](nn-sensorsclassextension-isensorclassextension.md) | The ISensorClassExtension interface provides methods that the sensor driver uses to communicate with the sensor platform (and, therefore, client applications) through the sensor class extension object. |
| [ISensorDriver interface](nn-sensorsclassextension-isensordriver.md) | The ISensorDriver interface provides callback methods that the sensor class extension uses to provide requests and notifications to the sensor driver. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [ISensorClassExtension::CleanupFile method](nf-sensorsclassextension-isensorclassextension-cleanupfile.md) | The ISensorClassExtension |
| [ISensorClassExtension::Initialize method](nf-sensorsclassextension-isensorclassextension-initialize.md) | The ISensorClassExtension |
| [ISensorClassExtension::PostEvent method](nf-sensorsclassextension-isensorclassextension-postevent.md) | The ISensorClassExtension |
| [ISensorClassExtension::PostStateChange method](nf-sensorsclassextension-isensorclassextension-poststatechange.md) | The ISensorClassExtension |
| [ISensorClassExtension::ProcessIoControl method](nf-sensorsclassextension-isensorclassextension-processiocontrol.md) | The ISensorClassExtension |
| [ISensorClassExtension::Uninitialize method](nf-sensorsclassextension-isensorclassextension-uninitialize.md) | The ISensorClassExtension |
| [ISensorDriver::OnClientConnect method](nf-sensorsclassextension-isensordriver-onclientconnect.md) | The ISensorDriver |
| [ISensorDriver::OnClientDisconnect method](nf-sensorsclassextension-isensordriver-onclientdisconnect.md) | The ISensorDriver |
| [ISensorDriver::OnClientSubscribeToEvents method](nf-sensorsclassextension-isensordriver-onclientsubscribetoevents.md) | The ISensorDriver |
| [ISensorDriver::OnClientUnsubscribeFromEvents method](nf-sensorsclassextension-isensordriver-onclientunsubscribefromevents.md) | The ISensorDriver |
| [ISensorDriver::OnGetDataFields method](nf-sensorsclassextension-isensordriver-ongetdatafields.md) | The ISensorDriver |
| [ISensorDriver::OnGetProperties method](nf-sensorsclassextension-isensordriver-ongetproperties.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedDataFields method](nf-sensorsclassextension-isensordriver-ongetsupporteddatafields.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedEvents method](nf-sensorsclassextension-isensordriver-ongetsupportedevents.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedProperties method](nf-sensorsclassextension-isensordriver-ongetsupportedproperties.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedSensorObjects method](nf-sensorsclassextension-isensordriver-ongetsupportedsensorobjects.md) | The ISensorDriver |
| [ISensorDriver::OnProcessWpdMessage method](nf-sensorsclassextension-isensordriver-onprocesswpdmessage.md) | The ISensorDriver |
| [ISensorDriver::OnSetProperties method](nf-sensorsclassextension-isensordriver-onsetproperties.md) | The ISensorDriver |
