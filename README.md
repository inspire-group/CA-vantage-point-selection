# CA-vantage-point-selection
An algorithm designed to select best vantage points for use by CAs.


The core algorithm is in compute vantage points.py.

It depends on the modules vantage_point_utils.py and histogram_sql.py.

random vantage points.py is designed to compute the effect of randomly selected vantage points.

cg_resilience.json is a JSON file containing a map with the following format:

{
  "Vantage point ASN": {"Domain ASN": resilience, ...},
  "Vantage point ASN": {"Domain ASN": resilience, ...},
  ...
}
Importantly, in the above format each "Vantage point ASN" entry must contain a dictionary containing the same "Domain ASN"s so that each of the dictionaries of resiliences has the same set of keys.   


as-weights.json contains a JSON file associating domain ASNs to their appropriate weight (the number of domains hosted in that AS) based on the certificate database (https://github.com/inspire-group/certificate-database). It has the following format:
{
  "Domain ASN": weight,
  "Domain ASN": weight,
  ...
}
as-weights.json must contain a weight for each Domain ASN used in cg_resilience.json for the script to work properly.
