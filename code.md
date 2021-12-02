- 👋 Hi, I’m @khalidq812
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
khalidq812/khalidq812 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// C++ program to print DFS traversal from
// a given vertex in a given graph
#include<iostream>
#include<list>
using namespace std;

// Graph class represents a directed graph
// using adjacency list representation
class Graph
{
	int V; // No. of vertices

	// Pointer to an array containing
	// adjacency lists
	list<int> *adj;

	// A recursive function used by DFS
	void DFSUtil(int v, bool visited[]);
  public:
	Graph(int V); // Constructor

	// function to add an edge to graph
	void addEdge(int v, int w);

	// DFS traversal of the vertices
	// reachable from v
	void DFS(int v);
};

Graph::Graph(int V)
{
	this->V = V;
	adj = new list<int>[V];
}

void Graph::addEdge(int v, int w)
{
	adj[v].push_back(w); // Add w to v’s list.
}

void Graph::DFSUtil(int v, bool visited[])
{
	// Mark the current node as visited and
	// print it
	visited[v] = true;
	cout << v << " ";

	// Recur for all the vertices adjacent
	// to this vertex
	list<int>::iterator i;
	for (i = adj[v].begin(); i != adj[v].end(); ++i)
		if (!visited[*i])
			DFSUtil(*i, visited);
}

// DFS traversal of the vertices reachable from v.
// It uses recursive DFSUtil()
void Graph::DFS(int v)
{
	// Mark all the vertices as not visited
	bool *visited = new bool[V];
	for (int i = 0; i < V; i++)
		visited[i] = false;

	// Call the recursive helper function
	// to print DFS traversal
	DFSUtil(v, visited);
}

// Driver code
int main()
{
	// Create a graph given in the above diagram
	Graph g(4);
	g.addEdge(0, 1);
	g.addEdge(0, 2);
	g.addEdge(1, 2);
	g.addEdge(2, 0);
	g.addEdge(2, 3);
	g.addEdge(3, 3);

	cout << "Following is Depth First Traversal"
			" (starting from vertex 2) \n";
	g.DFS(2);
  cout << endl;
	return 0;
}# CodeDocs.xyz Configuration File
#
# Rename this example to '.codedocs' and put it in the root directory of your
# repository. This file is optional, documentation will still be generated
# without it using sensible defaults.

#---------------------------------------------------------------------------
# CodeDocs Configuration
#---------------------------------------------------------------------------

# Include the Doxygen configuration from another file.
# The file must be a relative path with respect to the root of the repository.
# If any of the options in this doxyfile include a path (ie, INPUT), these
# paths will be considered relative to the root of the repository, not the
# location of the DOXYFILE.

DOXYFILE = doc/Doxyfile.in

# Specify external repository to link documentation with.
# This is similar to Doxygen's TAGFILES option, but will automatically link to
# tags of other repositories already using CodeDocs. List each repository to
# link with by giving its location in the form of owner/repository.
# For example:
#   TAGLINKS = doxygen/doxygen CodeDocs/osg
# Note: these repositories must already be built on CodeDocs.

TAGLINKS =

#---------------------------------------------------------------------------
# Doxygen Configuration
#---------------------------------------------------------------------------

# Doxygen configuration may also be placed in this file.
# Currently, the following Doxygen configuration options are available. Refer
# to http://doxygen.org/manual/config.html for detailed explanation of the
# options. To request support for more options, contact support@codedocs.xyz.
#
# ABBREVIATE_BRIEF =
# ALIASES =
# ALLEXTERNALS =
# ALLOW_UNICODE_NAMES =
# ALPHABETICAL_INDEX =
# ALWAYS_DETAILED_SEC =
# AUTOLINK_SUPPORT =
# BRIEF_MEMBER_DESC =
# BUILTIN_STL_SUPPORT =
# CALLER_GRAPH =
# CALL_GRAPH =
# CASE_SENSE_NAMES =
# CITE_BIB_FILES =
# CLASS_DIAGRAMS =
# CLASS_GRAPH =
# COLLABORATION_GRAPH =
# COLS_IN_ALPHA_INDEX =
# CPP_CLI_SUPPORT =
# DIAFILE_DIRS =
# DIRECTORY_GRAPH =
# DISABLE_INDEX =
# DISTRIBUTE_GROUP_DOC =
# DOTFILE_DIRS =
# DOT_FONTNAME =
# DOT_FONTSIZE =
# DOT_GRAPH_MAX_NODES =
# DOT_IMAGE_FORMAT =
# DOT_TRANSPARENT =
# DOXYFILE_ENCODING =
# ENABLED_SECTIONS =
# ENABLE_PREPROCESSING =
# ENUM_VALUES_PER_LINE =
# EXAMPLE_PATH =
# EXAMPLE_PATTERNS =
# EXAMPLE_RECURSIVE =
# EXCLUDE =
EXCLUDE_PATTERNS = *.py
# EXCLUDE_SYMBOLS =
# EXPAND_AS_DEFINED =
# EXPAND_ONLY_PREDEF =
# EXTENSION_MAPPING =
# EXTERNAL_GROUPS =
# EXTERNAL_PAGES =
# EXTRACT_ALL =
# EXTRACT_ANON_NSPACES =
# EXTRACT_LOCAL_CLASSES =
# EXTRACT_LOCAL_METHODS =
# EXTRACT_PACKAGE =
# EXTRACT_PRIVATE =
# EXTRACT_STATIC =
# EXT_LINKS_IN_WINDOW =
# FILE_PATTERNS =
# FORCE_LOCAL_INCLUDES =
# FORMULA_FONTSIZE =
# FORMULA_TRANSPARENT =
# FULL_PATH_NAMES =
# GENERATE_BUGLIST =
# GENERATE_DEPRECATEDLIST =
# GENERATE_LEGEND =
# GENERATE_TESTLIST =
# GENERATE_TODOLIST =
# GENERATE_TREEVIEW =
# GRAPHICAL_HIERARCHY =
# GROUP_GRAPHS =
# GROUP_NESTED_COMPOUNDS =
# HIDE_COMPOUND_REFERENCE= =
# HIDE_FRIEND_COMPOUNDS =
# HIDE_IN_BODY_DOCS =
# HIDE_SCOPE_NAMES =
# HIDE_UNDOC_CLASSES =
# HIDE_UNDOC_MEMBERS =
# HIDE_UNDOC_RELATIONS =
# HTML_COLORSTYLE_GAMMA =
# HTML_COLORSTYLE_HUE =
# HTML_COLORSTYLE_SAT =
# HTML_DYNAMIC_SECTIONS =
# HTML_EXTRA_FILES =
# HTML_EXTRA_STYLESHEET =
# HTML_FOOTER =
# HTML_HEADER =
# HTML_INDEX_NUM_ENTRIES =
# HTML_STYLESHEET =
# HTML_TIMESTAMP =
# IDL_PROPERTY_SUPPORT =
# IGNORE_PREFIX =
# IMAGE_PATH =
# INCLUDED_BY_GRAPH =
# INCLUDE_FILE_PATTERNS =
# INCLUDE_GRAPH =
# INCLUDE_PATH =
# INHERIT_DOCS =
# INLINE_GROUPED_CLASSES =
# INLINE_INFO =
# INLINE_INHERITED_MEMB =
# INLINE_SIMPLE_STRUCTS =
# INLINE_SOURCES =
# INPUT =
# INPUT_ENCODING =
# INTERACTIVE_SVG =
# INTERNAL_DOCS =
# JAVADOC_AUTOBRIEF =
# LAYOUT_FILE =
# MACRO_EXPANSION =
# MARKDOWN_SUPPORT =
# MAX_DOT_GRAPH_DEPTH =
# MSCFILE_DIRS =
# MULTILINE_CPP_IS_BRIEF =
# OPTIMIZE_FOR_FORTRAN =
# OPTIMIZE_OUTPUT_FOR_C =
# OPTIMIZE_OUTPUT_JAVA =
# OPTIMIZE_OUTPUT_VHDL =
# OUTPUT_LANGUAGE =
# PLANTUML_JAR_PATH =
# PREDEFINED =
# PROJECT_BRIEF =
# PROJECT_LOGO =
# PROJECT_NAME =
# PROJECT_NUMBER =
# QT_AUTOBRIEF =
# RECURSIVE =
# REFERENCED_BY_RELATION =
# REFERENCES_LINK_SOURCE =
# REFERENCES_RELATION =
# REPEAT_BRIEF =
# SEARCHENGINE =
# SEARCH_INCLUDES =
# SEPARATE_MEMBER_PAGES =
# SHORT_NAMES =
# SHOW_FILES =
# SHOW_GROUPED_MEMB_INC =
# SHOW_INCLUDE_FILES =
# SHOW_NAMESPACES =
# SHOW_USED_FILES =
# SIP_SUPPORT =
# SKIP_FUNCTION_MACROS =
# SORT_BRIEF_DOCS =
# SORT_BY_SCOPE_NAME =
# SORT_GROUP_NAMES =
# SORT_MEMBERS_CTORS_1ST =
# SORT_MEMBER_DOCS =
# SOURCE_BROWSER =
# SOURCE_TOOLTIPS =
# STRICT_PROTO_MATCHING =
# STRIP_CODE_COMMENTS =
# STRIP_FROM_INC_PATH =
# STRIP_FROM_PATH =
# SUBGROUPING =
# TAB_SIZE =
# TEMPLATE_RELATIONS =
# TREEVIEW_WIDTH =
# TYPEDEF_HIDES_STRUCT =
# UML_LIMIT_NUM_FIELDS =
# UML_LOOK =
# USE_MDFILE_AS_MAINPAGE =
# VERBATIM_HEADERS =
#
