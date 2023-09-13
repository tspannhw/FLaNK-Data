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
