import React, { useState } from 'react';
import { Terminal, Code, Database, Zap, Target, Briefcase, Coffee } from 'lucide-react';

const ProfileSection = ({ icon: Icon, title, content }) => (
  <div className="flex items-center space-x-2 p-2 hover:bg-gray-800 rounded transition-colors duration-200">
    <Icon className="text-red-500" />
    <div>
      <h3 className="font-bold text-white">{title}</h3>
      <p className="text-gray-300">{content}</p>
    </div>
  </div>
);

const InteractiveProfile = () => {
  const [showMore, setShowMore] = useState(false);

  return (
    <div className="max-w-2xl mx-auto bg-black shadow-lg rounded-lg overflow-hidden border border-red-500">
      <div className="p-4 bg-gradient-to-r from-red-700 to-red-900 text-white">
        <h1 className="text-3xl font-bold">👋 Hi! I'm Pietro Cavaliere</h1>
        <p className="mt-2 text-gray-200">Web & Backend Developer passionate about cybersecurity</p>
      </div>
      
      <div className="p-4 bg-gray-900">
        <ProfileSection 
          icon={Terminal} 
          title="Web & Backend Development" 
          content="Specialized in backend development, hardening, and MySQL database management, with strong expertise in Python."
        />
        <ProfileSection 
          icon={Target} 
          title="Goal" 
          content="To become a Full Stack Developer, blending my development skills with a passion for cybersecurity."
        />
        <ProfileSection 
          icon={Coffee} 
          title="Motivation" 
          content="I've been coding since childhood because I love creating new things and solving problems efficiently."
        />
        
        {showMore && (
          <>
            <ProfileSection 
              icon={Code} 
              title="Coding Style" 
              content="Clean and organized, with a multitasking and multi-threaded approach to tackle every challenge."
            />
            <ProfileSection 
              icon={Zap} 
              title="Aspiration" 
              content="To become an Ethical Hacker."
            />
          </>
        )}
        
        <button 
          onClick={() => setShowMore(!showMore)} 
          className="mt-4 px-4 py-2 bg-red-600 text-white rounded hover:bg-red-700 transition-colors duration-200"
        >
          {showMore ? 'Show Less' : 'Discover More'}
        </button>
      </div>
    </div>
  );
};

export default InteractiveProfile;
