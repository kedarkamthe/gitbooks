# Event-Driven Architecture

![Different approaches for implementing event driven architecture](/broken/files/-LoteQt5G_yswm9V7M-8)

## **Event Notification**

![Event Notification](/broken/files/-LotkG7i21oKhgcb5oEZ)

![Decoupled communication](/broken/files/-Lotkz1ZfcTNubhe2tqA)

![Pros and Cons with ](/broken/files/-LotkUVtfspoIlobseaV)

## Event Carried State Transfer

![Event Carried State Transfer](/broken/files/-LotlSBpoIYccRnli6mz)

In this method DB details of customer is replicated to insurance service which will be used in case of changes in detail event occur. so Insurance service don't have to talk to Customer management service even though customer service is down Insurance service will work(With Eventually consistent data). Insurance service can refer tables/data which is required to it and replicated (only data/table required by Insurance service). But with this approach below are the pros and cons.

![Pros and Cons of Event-carried State Transfer](/broken/files/-Lotmkssn1E38-CUWGG8)

## **Event Sourcing**

![Creating event and storing in event logs for replaying in future](/broken/files/-Lotnkn8RRuCz-YH07r1)

![Building application state by replaying logs](/broken/files/-LotoVs20VZpt2phIYIg)

You can build application state of application at any point of time by replaying the events present in logs.

This can be combination of events and snapshot at given frequency. e.g. in case of banking you can hold the events till end of financial year once new financial year is started it takes snapshot of application state and start building new events from this snapshot.(can clean existing events or can keep existing events to draw some insights)

### **Best Examples of Event Sourcing**

**From Developer View**  Version control system(git,cvs)&#x20;

**From Business View** Counting ledger which holds information of each debit and credit in account.

![Pros and Cons of Event Sourcing](/broken/files/-Lot_Oz_xwHA2BTaBebY)

## CQRS

![Need to be used carefully and to be if required](/broken/files/-LotdWyH_KkidVyoihbQ)



Source : [https://www.youtube.com/watch?v=STKCRSUsyP0](https://www.youtube.com/watch?v=STKCRSUsyP0)



