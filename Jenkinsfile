
allprojects  {	
	apply plugin: 'maven'
	group = "com.cts"
	ext.snapshotVersion =System.getenv("SNAPSHOT")
	ext.baseversionupdate=System.getenv("BUILD_NUM")
	ext.baseVersion = "0.1" + (snapshotVersion ? "" : "$baseversionupdate" )
	version = "$baseVersion" + (snapshotVersion ? "-SNAPSHOT" : "")  
	 }

subprojects {
  apply plugin: 'java'
  apply plugin: 'jacoco'
  sourceCompatibility = 1.8
  targetCompatibility = 1.8
  test {
	ignoreFailures = true
	exclude '**/*IT*'
	}
  repositories {
    maven { url "http://54.89.170.23:8081/nexus/content/repositories/central/" }
	}  
  jacocoTestReport { 
     reports { 
		 xml.enabled true 
         html.enabled false  
		 }    
		}
}
		
