# MsSQL-DRIVE-With-elFinder-
Microsoft SQL Server Database Connect with elFinder

Connect your Microsoft SQL Server Database with elFinder

$opts = array(
	// 'debug' => true,
	'roots' => array(
		array(
			'driver'        => 'LocalFileSystem',           // driver for accessing file system (REQUIRED)
			'path'          => '../files/',                 // path to files (REQUIRED)
			'URL'           => dirname($_SERVER['PHP_SELF']) . '/../files/', // URL to files (REQUIRED)
			'uploadDeny'    => array('all'),                // All Mimetypes not allowed to upload
			'uploadAllow'   => array('image', 'text/plain'),// Mimetype `image` and `text/plain` allowed to upload
			'uploadOrder'   => array('deny', 'allow'),      // allowed Mimetype `image` and `text/plain` only
			'accessControl' => 'access'                     // disable and hide dot starting files (OPTIONAL)
		),
		array (
				'driver'        => 'MSSQL',				
				'host'          => 'localhost', 
				'user'          => 'user name',
				'pass'          => 'your password',
				'alias'			    => 'MsSQL DATABASE',
				'db'            => 'elfinderdatabase',				
				'files_table'   => 'elfinder_file',				
				'path'          => 1,
				'uploadDeny'    => array('all'),                // All Mimetypes not allowed to upload
				'uploadAllow'   => array('image', 'text/plain'),// Mimetype `image` and `text/plain` allowed to upload
				'uploadOrder'   => array('deny', 'allow'),      // allowed Mimetype `image` and `text/plain` only				
				'tmpPath' 		=> '../files/.tmp',
				'tmbPath' 		=> '../files/.tmb',
				'tmbURL'  		=> dirname($_SERVER['PHP_SELF']) . '/../files/.tmb',
				'defaults'   	=> array('read' => true, 'write' => true, 'locked' => false, 'hidden' => false) // Lock root directory
				
				)
	)
);
