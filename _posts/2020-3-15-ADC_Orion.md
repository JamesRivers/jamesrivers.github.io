---
layout: post
title: ADC Orion


ADC Orion allows you to synchronize an ADCASDB database with the Versio Automation database (VersioDB).

This allows legacy ADC clients to schedule content ingested from Content Portal.There are two types of synchronization

-Full sync.
--This allows you to copy all records stored in source database(only in dbo.ASDB and dbo.ASSEG tables in ASDB) into the destination database and vice versa. Events are moved to the destination database with minimum changes.

-Delta sync.
--Allows real time translation of all changes of DB records/events between source and destination databases in both directions Source -> Destination andDestination -> Source.

## ADC Orion Overview ##

<https://vimeo.com/user3008926/review/398268606/0f41392fb6>
