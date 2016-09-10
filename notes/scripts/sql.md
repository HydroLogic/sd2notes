





# ELEMENTS

```sql
SELECT Prop.PropertyID, PROP.ExtPropertyID, ADDR.StateAbbreviation, NumOfStories, YearBuilt, BuildingType, OccupancyType, BasementClass, Addrmatch, Addr.Latitude/1000000. GeoLat, ADDR.Longitude/1000000. GeoLon, ADDR.PostalCode GeoZip, Elevation Elevation_cm ,SITE.STR_TIV, SITE.CON_TIV, SITE.TE_TIV, AAL.GU GU_AAL FROM (SELECT * FROM IF_EXP_mrs_aal_huc07.dbo.property WHERE PortfolioID = 2) PROP FULL JOIN (SELECT * FROM IF_EXP_mrs_aal_huc07.dbo.site WHERE PortfolioID = 2) SITE ON PROP.ExtPropertyID = Site.ExtSiteID FULL JOIN (SELECT * FROM IF_EXP_mrs_aal_huc07.dbo.Address WHERE PortfolioID = 2) ADDR ON PROP.EXTPropertyID = ADDR.ExtPropertyID FULL JOIN (SELECT * FROM IF_RES_mrs_aal_huc07.dbo.PML WHERE PMLLevelType = 'LOCATION' AND AnalysisRunID =3 AND RetPeriod = 0) AAL ON AAL.RefID = PROP.PropertyID 
```