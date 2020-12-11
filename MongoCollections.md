# MongoDB Collection Overview

 This document contains information about the data stored in the Mongo Database for this project. Each collection has a specific data type that can be inserted from the API or from running simulations

## scenarios

**Example Object:**
```json
{
	"_id" : ObjectId("5fcc12d79b20f238c4ed001c"),
	"id" : "A",
	"desc" : "J:Full O:Full Y:Overbooked",
	"FlightNum" : 9992,
	"Dept" : "MDW",
	"Arriv" : "PHX",
	"cabins" : {
		"J" : {
			"passengers" : 18,
			"capacity" : 18
		},
		"O" : {
			"passengers" : 26,
			"capacity" : 26
		},
		"Y" : {
			"passengers" : 161,
			"capacity" : 154
		}
	}
}
```
**Description:**
Contains information about an oversale scenario. This is how users can choose different inputs for the simulation to train models without bias. 

## Simulations
**Example Object:**
```json
{
	"_id" : ObjectId("5fcd37ea43c5e9f3fbc68a93"),
	"id" : "6bf384bd-37fd-11eb-8450-9cb6d0b8d800",
	"scenario_name" : "A",
	"status" : "COMPLETE",
	"parameters" : {
	},
	"timestamp" : "2020-12-06T14:58:34.230700"
}
```
**Description:**
This object is generated when a simulation begins, it contains information about the simulation as a whole

## Simulation_Events
**Example Object:**
```json
{
	"_id" : ObjectId("5fcd37eb43c5e9f3fbc68a94"),
	"sim_id" : "6bf384bd-37fd-11eb-8450-9cb6d0b8d800",
	"event_list" : [
		{
			"pid" : 205,
			"event_type" : "CHECK_IN",
			"details" : {
				"name" : "Tarik Powell"
			},
			"time" : "2020-01-12T01:00:01"
		},
		{
			"pid" : 226,
			"event_type" : "BID",
			"details" : {
				"name" : "Daphne Tucker",
				"amount" : 400,
				"ETC" : 250,
				"response" : 0
			},
			"time" : "2020-01-12T22:01:53"
		},
	]
}
```
**Description:**
Contains a chronological list of events for a simulation, including a key and relevant details

## Simulation_Passengers
**Example Object:**
```json
{
	"_id" : ObjectId("5fcd444ce2187c43c28d5a04"),
	"sim_id" : "cd3592a1-3804-11eb-ae66-9cb6d0b8d800",
	"vol_list" : [
		{
			"bid_history" : [
				{
					"accepted" : false,
					"bid_id" : 49,
					"etc_comp" : 200,
					"initiated_by" : "USER",
					"miles_comp" : 750,
					"timestamp" : "2020-01-12T10:57:01",
					"vol_id" : 203,
					"vol_name" : "Tarik Powell"
				},	
				{
					"accepted" : true,
					"bid_id" : 51,
					"etc_comp" : 250,
					"initiated_by" : "USER",
					"miles_comp" : 1000,
					"timestamp" : "2020-01-12T11:13:16",
					"vol_id" : 203,
					"vol_name" : "Tarik Powell"
				}
			],
			"compensation" : [
				{
					"comp_amount" : 450,
					"comp_id" : 1,
					"comp_type" : "MEAL",
					"vol_id" : 1
				}
			],
			"vol_info" : {
				"cabin" : "J",
				"fin_dest" : "PHX",
				"id" : 203,
				"name" : "Tarik Powell",
				"processed" : true,
				"vol_method" : "DEFAULT"
			}
		},
	]
}
```
**Description:**
Contains all relevant data for each passenger during a simulation

## Simulation_Volunteers

**Description:**
Contains the same information as Simulation_Passengers, with volunteers only. This is updated real-time during the simulation itself. 

## NewoBj
**Example Object:**
```json
\
```
**Description:**

## NewoBj
**Example Object:**
```json
\
```
**Description:**
