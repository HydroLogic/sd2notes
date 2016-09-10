







# Python Snippits

		'DRIVER={SQL Server};SERVER=chiareRDOmega\sqlserver2012;UID=ifadmin;PWD=ifadmin'

		px_x = 0.01016667
		rot_y = 0.0
		rot_x = 0.0
		px_y = -0.01016763
		upleft_x_px_cent = -125.00000000
		upleft_y_px_cent = 53.00000000

		hours = ['00','01','02','03','04','05','06','07','08','09','10','11','12','13','14','15','16','17','18','19','20','21','22','23']

		hucs = {1:'01',2:'02',3:'03',4:'04',5:'05',6:'06',7:'07',8:'08',9:'09',10:'10',11:'11',12:'12',13:'13',14:'14',15:'15',16:'16',17:'17',18:'18',19:'01',20:'02',21:'03',22:'04',23:'05',24:'06',25:'07',26:'08',27:'09',28:'10',29:'11',30:'12',31:'13',32:'14',33:'15',34:'16',35:'17',36:'18',37:'01',38:'02',39:'03',40:'04',41:'05',42:'06',43:'07',44:'08',45:'09',46:'10',47:'11',48:'12',49:'13',50:'14',51:'15',52:'16',53:'17',54:'18'}

# Rasterio

		rio stack fp30m_huc05_fp100m.tif clipped30m.tif --co bigtiff=yes --co tiled=true --co blockxsize=256 --co blockysize=256 --co compress=LZW -f VRT -o stk_merged.vrt


# GDAL

		gdal_calc -A 20160907_FloodPlain_Analysis_HERMINE_Grid__FINAL_HAZ_LongLat.tif --outfile=20160907_FloodPlain_Analysis_HERMINE_1.tif --calc="1*(A>-9999)" --type="Int16" --NoDataValue=-9999 --overwrite --co tiled=yes --co compress=lzw

		gdaladdo -ro SS_100m_fldht_ft.tif 2 4 8 16 32	

		gdal_rasterize -3d -l ras100yr_dpth -a_nodata -9999 -tr 0.00115 0.00115 -tap -ot Float32 -co tiled=yes -co bigtiff=yes -co compress=lzw ras100yr_dpth.vrt ras100yr_dpth.tif

		gdaladdo -ro --config COMPRESS_OVERVIEW DEFLATE ras100yr_dpth.tif 2 4 8 16

		gdal_rasterize -a NetFH_Meter -l 20160419_FloodPlain_Analysis_LP3_LOW2011_Grid__FINAL_HAZ_LongLat -a_nodata -9999 -tr 0.00115 0.00115 -tap -co tiled=yes -co bigtiff=yes -co compress=lzw -ot Float32 20160419_FloodPlain_Analysis_LP3_LOW2011_Grid__FINAL_HAZ_LongLat.vrt 20160419_FloodPlain_Analysis_LP3_LOW2011_Grid__FINAL_HAZ_LongLat.tif

		gdal_rasterize -a NetFH_Meter -l 20160420_FloodPlain_Analysis_l2016scenarios_max_Grid__FINAL_HAZ_LongLat -a_nodata -9999 -tr 0.00115 0.00115 -tap -co tiled=yes -co bigtiff=yes -co compress=lzw -ot Float32 20160420_FloodPlain_Analysis_l2016scenarios_max_Grid__FINAL_HAZ_LongLat.vrt 20160420_FloodPlain_Analysis_l2016scenarios_max_Grid__FINAL_HAZ_LongLat.tif


