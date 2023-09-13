# FLaNK-Data
Data


### Postgresql table

````

CREATE TABLE public.repos (
	repo_id text NOT NULL,
	repo_name text NULL,
	primary_language text NULL,
	description text NULL,
	stars text NULL,
	forks text NULL,
	pull_requests text NULL,
	pushes text NULL,
	total_score text NULL,
	contributor_logins text NULL,
	collection_names text NULL,
	startms text NULL,
	endms text NULL,
	latency text NULL,
	ratelimitremaining text NULL,
	message text NULL,
	ts text NULL,
	processdate text NULL,
	uuid text NULL,
	rowcount text NULL,
	ratelimitremainingmin text NULL,						
	
	CONSTRAINT repospkid PRIMARY KEY (repo_id)
);



````

### Flink SQL Table

````

CREATE TABLE `ssb`.`Meetups`.`ossinsights` (
  `repo_id` VARCHAR(2147483647),
  `repo_name` VARCHAR(2147483647),
  `primary_language` VARCHAR(2147483647),
  `description` VARCHAR(2147483647),
  `stars` VARCHAR(2147483647),
  `forks` VARCHAR(2147483647),
  `pull_requests` VARCHAR(2147483647),
  `pushes` VARCHAR(2147483647),
  `total_score` VARCHAR(2147483647),
  `contributor_logins` VARCHAR(2147483647),
  `collection_names` VARCHAR(2147483647),
  `startms` VARCHAR(2147483647),
  `endms` VARCHAR(2147483647),
  `latency` VARCHAR(2147483647),
  `ratelimitremaining` VARCHAR(2147483647),
  `message` VARCHAR(2147483647),
  `ts` VARCHAR(2147483647),
  `processdate` VARCHAR(2147483647),
  `uuid` VARCHAR(2147483647),
  `rowcount` VARCHAR(2147483647),
  `ratelimitremainingmin` VARCHAR(2147483647),
  `eventTimeStamp` TIMESTAMP(3) WITH LOCAL TIME ZONE METADATA FROM 'timestamp',
  WATERMARK FOR `eventTimeStamp` AS `eventTimeStamp` - INTERVAL '3' SECOND
) WITH (
  'deserialization.failure.policy' = 'ignore_and_log',
  'properties.request.timeout.ms' = '120000',
  'format' = 'json',
  'properties.bootstrap.servers' = 'kafka:9092',
  'connector' = 'kafka',
  'properties.transaction.timeout.ms' = '900000',
  'topic' = 'ossinsights',
  'scan.startup.mode' = 'group-offsets',
  'properties.auto.offset.reset' = 'earliest',
  'properties.group.id' = 'ossisnightflinkssb1'
)



````
