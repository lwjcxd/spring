SConscript(['rts/SConstruct'])
Import('env')
prefix=ARGUMENTS.get('prefix',"/usr/local")
include_path=['rts']
centralbuild = env.SharedLibrary('centralbuild',['CentralBuildAI/GroupAI.cpp','CentralBuildAI/TestAI.cpp'],CPPPATH=include_path)
mmhandler = env.SharedLibrary('mmhandler',['MetalMakerAI/GroupAI.cpp','MetalMakerAI/TestAI.cpp'],CPPPATH=include_path)
SimpleForm = env.SharedLibrary('SimpleForm',['SimpleFormationAI/GroupAI.cpp','SimpleFormationAI/TestAI.cpp'],CPPPATH=include_path)
test = env.SharedLibrary('test',['TestGlobalAI/GlobalAI.cpp','TestGlobalAI/TestAI.cpp'],CPPPATH=include_path)
gamedir="/games/taspring"
env.InstallAs([
	prefix+gamedir+"/aidll/centralbuild.so",
	prefix+gamedir+"/aidll/mmhandler.so",
	prefix+gamedir+"/aidll/SimpleForm.so",
	prefix+gamedir+"/aidll/globalai/test.so",
	],[centralbuild,mmhandler,SimpleForm,test])
env.Alias('install',prefix+gamedir+"/aidll")
