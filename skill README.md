# Geospatial Graph RAG Skill

A comprehensive Claude skill for building location-aware Graph RAG systems using GeoSPARQL, RDF, and Virtuoso Universal Server.

## What We Built

This skill transforms your geospatial Graph RAG GitHub repository into an actionable, reusable skill that Claude can use to help with:

- Converting GeoJSON to RDF with GeoSPARQL annotations
- Setting up Virtuoso with spatial extensions
- Constructing complex spatial queries
- Building location-aware RAG applications
- Analyzing retail/logistics intelligence data

## Skill Structure

```
geospatial-graph-rag.skill (21KB)
├── SKILL.md                              # Main skill documentation
├── scripts/                              # Executable utilities
│   ├── convert_geojson_to_rdf.py        # GeoJSON → RDF converter
│   ├── load_to_virtuoso.py              # Virtuoso data loader
│   └── spatial_query_helper.py          # Common spatial query tool
├── references/                           # Detailed documentation
│   ├── architecture-layers.md           # 10-layer architecture guide
│   ├── geosparql-queries.md            # Query pattern library
│   └── virtuoso-setup.md               # Setup & configuration guide
└── assets/                               # Example data
    └── example-stores.geojson           # Sample retail locations
```

## What's Included

### 1. Core Documentation (SKILL.md)
- Quick start guide with example pipeline
- Architecture overview (10-layer system)
- Common workflows (ingestion, querying, RAG integration)
- Tool integration guidance
- Performance optimization tips
- Troubleshooting guide

### 2. Python Scripts (scripts/)
All scripts are executable and ready to use:

**convert_geojson_to_rdf.py**
- Converts GeoJSON files to RDF/Turtle format
- Adds GeoSPARQL annotations automatically
- Supports all geometry types (Point, LineString, Polygon, Multi*)
- Generates proper WKT literals

**load_to_virtuoso.py**
- Loads RDF data into Virtuoso named graphs
- Handles authentication
- Can clear graphs before loading
- Verifies loads by counting triples

**spatial_query_helper.py**
- Pre-built common spatial queries
- No SPARQL knowledge required
- Commands: within-distance, nearest, bbox, within-polygon, count-types
- Outputs in table or JSON format

### 3. Reference Documentation (references/)

**architecture-layers.md** (9KB)
- Complete 10-layer architecture breakdown
- Layer 1-3: Data foundation (storage, versioning, markup)
- Layer 4-7: Semantic layer (JSON-LD, ontologies, URIs)
- Layer 8-10: Query & generation (Virtuoso, publication, RAG)
- Implementation examples for each layer
- Common challenges and solutions

**geosparql-queries.md** (9KB)
- 20+ query patterns with examples
- Distance queries (within, nearest)
- Spatial relationships (contains, intersects, touches)
- Buffer zones and bounding boxes
- Complex analysis (service areas, competitive analysis)
- Performance optimization patterns
- Virtuoso-specific functions reference

**virtuoso-setup.md** (10KB)
- Docker and native installation
- Configuration for geospatial extensions
- Data loading strategies
- Spatial indexing setup
- SPARQL endpoint configuration
- Performance tuning
- Monitoring and troubleshooting
- Python integration examples

### 4. Example Data (assets/)

**example-stores.geojson**
- Sample retail locations in Abuja, Nigeria
- Point features (3 stores)
- Polygon feature (municipal boundary)
- Ready for testing conversions

## How to Use This Skill

### Installation
1. Download `geospatial-graph-rag.skill`
2. Upload to Claude (drag & drop in chat)
3. Claude will automatically recognize and use it when needed

### Triggering the Skill
The skill activates when you ask Claude about:
- "Convert this GeoJSON to RDF"
- "Setup Virtuoso with spatial extensions"
- "Find stores near this location"
- "Build a geospatial Graph RAG system"
- "Analyze spatial relationships in my data"

### Example Workflows

**Quick Data Pipeline:**
```bash
# Claude can guide you through:
python scripts/convert_geojson_to_rdf.py your_data.geojson output.ttl
python scripts/load_to_virtuoso.py output.ttl --graph http://your-graph-uri
python scripts/spatial_query_helper.py nearest --point "7.49,9.08" --limit 10
```

**Building a System:**
Claude will reference the architecture guide to help you:
1. Design your 10-layer stack
2. Choose appropriate tools (MinIO, Virtuoso, etc.)
3. Implement data ingestion pipelines
4. Create spatial queries
5. Integrate with RAG applications

## Technical Details

### Dependencies
Scripts require:
- Python 3.7+
- rdflib
- SPARQLWrapper

Install with: `pip install rdflib SPARQLWrapper`

### Standards Implemented
- GeoSPARQL 1.0 (OGC standard)
- WKT (Well-Known Text)
- WGS84 coordinate system
- RDF/RDFS/OWL
- JSON-LD

### Tested With
- Virtuoso Universal Server 7.x
- QGIS-compatible data formats
- Nigerian geospatial datasets (Abuja region)

## Design Principles

This skill follows Claude skill best practices:

1. **Progressive Disclosure**: Metadata → SKILL.md → References as needed
2. **Concise Core**: SKILL.md under 500 lines, details in references
3. **Executable Scripts**: Deterministic operations as Python scripts
4. **Clear Triggers**: Description specifies exact use cases
5. **Practical Examples**: Real-world patterns from retail intelligence

## Use Cases Supported

- **Retail Intelligence**: Store location analysis, service area mapping
- **Logistics**: Route optimization, delivery zone analysis
- **Real Estate**: Property proximity analysis, market comparisons
- **Urban Planning**: Infrastructure mapping, zoning analysis
- **Environmental**: Sensor networks, coverage analysis

## Based On

This skill was created from your geospatial Graph RAG repository:
https://github.com/Ajared/geospatialGraphRAG

The skill distills the 10-layer architecture, tool selections, and implementation patterns into a reusable format that Claude can apply to new projects.

## Next Steps

1. **Test the Skill**: Upload to Claude and try example queries
2. **Customize Scripts**: Modify for your specific data formats
3. **Extend References**: Add your own query patterns
4. **Share**: Distribute to team members working on spatial projects

## About Skill Creation

Created using Claude's skill-creator framework following best practices for:
- Workflow-based organization
- Progressive disclosure of complexity
- Executable, tested scripts
- Comprehensive reference documentation
- Real-world use case focus

Total size: 21KB (efficient context usage)
Total files: 8 (organized structure)
Documentation: ~28KB across references

---

**Ready to build location-aware AI applications!** 🗺️
