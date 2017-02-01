# Series_Tiempo

# Base ENILEMS 2012

temporal1<-tempfile()
download.file("http://www.beta.inegi.org.mx/contenidos/proyectos/enchogares/modulos/enilems/2012/microdatos/enilems12_bd_dbf.zip",temporal1)
files=unzip(temporal1, list = TRUE)$Name
unzip(temporal1,files=files[grepl("dbf",files)])
install.packages("foreign")
require(foreign)
ENILEMS<-data.frame(read.dbf("cbasico.dbf"))
